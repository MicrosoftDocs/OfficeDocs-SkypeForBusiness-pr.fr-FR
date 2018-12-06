---
title: "Lync Server 2013 : Conf. d’une jonction avec la déviation du trafic mult."
TOCTitle: Configuration d’une jonction avec la déviation du trafic multimédia
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398792(v=OCS.15)
ms:contentKeyID: 49298271
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Suivez ces étapes pour configurer une jonction avec la déviation du trafic multimédia activée. Pour configurer une jonction avec la déviation du trafic multimédia activée, reportez-vous à [Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md). La déviation du trafic multimédia est utile lorsque vous voulez réduire le nombre de serveurs de médiation déployés. Un pool de serveurs de médiation est généralement déployé sur un site central et contrôle des passerelles sur des sites de succursale. L’activation de la déviation du trafic multimédia permet aux médias de passer des appels RTC (réseau téléphonique commuté) à partir de clients situés sur les sites de succursale directement par les passerelles de ces sites. L’acheminement des appels sortants Lync Server 2013 et les stratégies Voix Entreprise doivent être configurés correctement pour que les appels RTC passés à partir des clients sur un site de succursale soient acheminés vers la passerelle appropriée.

Nous vous conseillons vivement d’activer la déviation du trafic multimédia. Cependant, avant de l’activer sur une jonction SIP, assurez-vous que votre fournisseur de jonctions SIP compétent prend en charge cette option et qu’il est en mesure de satisfaire aux exigences d’activation du scénario. Plus spécifiquement, le fournisseur doit disposer des adresses IP des serveurs sur le réseau interne de votre organisation. Si le fournisseur ne peut pas prendre en charge ce scénario, la déviation du trafic multimédia échoue. Pour plus d’informations, reportez-vous à [Planification de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) dans la documentation de planification.

> [!NOTE]  
> La déviation du trafic multimédia ne fonctionnera pas avec chaque passerelle RTC (réseau téléphonique commuté), système IP-PBX et SBC (Session Border Controller). Microsoft a testé une série de passerelles RTC et de systèmes SBC avec l’aide de partenaires agréés et a également procédé à des tests avec les systèmes IP-PBX de Cisco. La déviation du trafic multimédia n’est prise en charge qu’avec les produits et versions recensés dans « Infrastructure qualifiée pour Microsoft Lync » à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=214406%26clcid=0x40c">http://go.microsoft.com/fwlink/?linkid=214406&amp;clcid=0x40C</a>.

Une configuration de jonction telle que décrite ci-dessous regroupe un ensemble de paramètres appliqués aux jonctions auxquelles cette configuration de jonction est affectée. Une configuration de jonction particulière peut avoir une étendue globale (applicable à toutes les jonctions qui ne disposent pas de configuration de pool ou de site plus spécifique) ou avoir comme étendue un site ou un pool. La configuration de jonction au niveau du pool sert à appliquer une configuration de jonction spécifique à une jonction unique.

## Pour configurer une jonction avec la déviation du trafic multimédia

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.

4.  Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :
    
      - Double-cliquez sur une jonction existante (par exemple, la jonction **Global** ) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.
    
      - Cliquez sur **Nouvelle**, puis sélectionnez une étendue pour la nouvelle configuration de jonction :
        
          - **Jonction de site** : choisissez le site de la configuration de jonction dans **Sélectionner un site**, puis cliquez sur **OK**. Notez que si une configuration de jonction a déjà été créée pour un site, celui-ci ne s’affiche pas dans **Sélectionner un site**. Cette configuration de jonction sera appliquée à toutes les jonctions du site.
        
          - **Jonction de pool** : choisissez le nom de la jonction à laquelle cette configuration de jonction s’applique. Cette jonction peut être la jonction racine ou toute jonction supplémentaire définie dans le Générateur de topologie. Dans **Sélectionner un site**, cliquez sur **OK**. Notez que si une configuration de jonction a déjà été créée pour une jonction spécifique, celle-ci ne s’affiche pas dans **Sélectionner un site**.
    
    > [!NOTE]  
    > Une fois que vous avez sélectionné l’étendue de la configuration de jonction, elle n’est plus modifiable.<br />
    Le champ <strong>Nom</strong> est prérempli et comporte le nom du site ou service associé à la configuration de jonction. Ce nom n’est pas modifiable.

5.  Spécifiez une valeur dans **Nombre maximal de boîtes de dialogue anticipées prises en charge**. Il s’agit du nombre maximal de réponses dirigées qu’une passerelle RTC (réseau téléphonique commuté), IP-PBX ou qu’un contrôleur de session en périphérie (SBC, Session Border Controller) d’un fournisseur de services de téléphonie et Internet (ITSP) peut recevoir à une INVITATION envoyée au serveur de médiation. La valeur par défaut est 20.
    
    > [!NOTE]  
    > Avant de modifier cette valeur, consultez votre fournisseur de services ou le fabricant de matériel pour obtenir de plus amples informations sur les capacités de votre système.

6.  Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement**  :
    
      - **Requis** : le chiffrement SRTP (Secure Real-time Transport Protocol) doit être utilisé pour aider à protéger le trafic entre le serveur de médiation et la passerelle ou le système PBX (Private Branch Exchange).
    
      - **Facultatif** : le chiffrement SRTP sera utilisé s’il est pris en charge par le fournisseur de services ou le fabricant.
    
      - **Non pris en charge** : le chiffrement SRTP n’étant pas pris en charge pas le fournisseur de services ou le fabricant, il ne peut pas être utilisé.

7.  Activez la case à cocher **Activer la déviation du trafic multimédia** si vous souhaitez que le média contourne le serveur de médiation afin d’être traité par le pair de jonction.
    
    > [!IMPORTANT]  
    > Pour que la déviation du trafic multimédia fonctionne correctement, la passerelle RTC, un IP-PBX ou un contrôleur de session en périphérie d’un fournisseur de services de téléphonie et Internet (ITSP) doit prendre en charge certaines fonctionnalités. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-planning-for-media-bypass.md">Planification de la déviation du trafic multimédia dans Lync Server 2013</a> dans la documentation de planification.

8.  Activez la case à cocher **Traitement multimédia centralisé** si un point de terminaison média connu existe (par exemple, une passerelle RTC où la terminaison multimédia possède la même adresse IP que la terminaison de signalisation). Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.

9.  Si l’homologue de jonction prend en charge la réception les demandes SIP REFER provenant du serveur de médiation, activez la case à cocher **Activer la référence d’appel vers la passerelle**.
    
    > [!NOTE]  
    > Si vous désactivez cette option alors que l’option <strong>Activer la déviation du trafic multimédia</strong> est sélectionnée, des paramètres supplémentaires sont requis. Si le pair de jonction ne prend pas en charge la réception des requêtes de RÉFÉRENCE SIP du serveur de médiation et si la déviation du trafic multimédia est activée, vous devez également exécuter l’applet de commande <strong>Set-CsTrunkConfiguration</strong> pour désactiver le RTCP pour les appels en cours ou en attente afin de prendre en charge les conditions appropriées à la déviation du trafic multimédia. Pour plus d’informations, reportez-vous à la documentation <a href="lync-server-2013-lync-server-management-shell.md">Lync Server Management Shell</a> documentation.<br />
    En guise d’alternative, vous pouvez sélectionner <strong>Activer la référence avec un contrôle d’appel tiers</strong> si vous souhaitez que les appels transférés soient soumis à la déviation du trafic multimédia et que la passerelle ne prend pas en charge les demandes SIP REFER.

10. (Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation RTC à cette configuration de jonction. Les utilisations RTC associées à cette configuration de jonction seront appliquées à tous les appels entrants via la jonction qui ne provient pas d’un point de terminaison Lync. Pour gérer les enregistrements d’utilisation RTC associés à une configuration de jonction, appliquez l’une des méthodes suivantes :
    
      - Pour sélectionner un ou plusieurs enregistrements dans la liste de tous les enregistrements d’utilisation RTC disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette configuration de jonction, puis cliquez sur **OK**.
    
      - Pour supprimer un enregistrement d’utilisation RTC de cette configuration de jonction, sélectionnez l’enregistrement, puis cliquez sur **Supprimer**.
    
      - Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette configuration de jonction, procédez comme suit :
        
        1.  Cliquez sur **Nouveau**.
        
        2.  Dans le champ **Nom**, indiquez un nom descriptif unique pour l’enregistrement.
            
            > [!NOTE]  
            > Le nom de l’enregistrement d’utilisation RTC doit être unique au sein du déploiement Voix Entreprise. Une fois l’enregistrement enregistré, le champ <strong>Nom</strong> ne peut plus être modifié.        
        3.  Appliquez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation RTC :
            
              - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.
            
              - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            
              - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, reportez-vous à [Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Pour modifier un itinéraire associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, reportez-vous à [Modifier un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Cliquez sur **OK**.
    
      - Pour modifier un enregistrement d’utilisation RTC déjà associé à cette configuration de jonction, procédez comme suit :
        
        1.  Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.
        
        2.  Appliquez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation RTC :
            
              - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.
            
              - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            
              - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, reportez-vous à [Créer un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Pour modifier un itinéraire associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, reportez-vous à [Modifier un itinéraire de communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Cliquez sur **OK**.
    
    > [!IMPORTANT]  
    > Il est important d’associer les enregistrements d’utilisation RTC en fonction de l’homologue serveur de médiation associé à la jonction configurée. Si l’homologue serveur de médiation est une passerelle RTC ou un contrôleur SBC, il est recommandé de ne pas associer la configuration de jonction à un enregistrement d’utilisation RTC acheminé vers une destination RTC ou d’autres systèmes en aval connectés via Lync Server.

11. Organisez les enregistrements d’utilisation RTC pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation RTC, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!IMPORTANT]  
    > L’ordre des enregistrements d’utilisation RTC dans la liste de la configuration de jonction a son importance. Lync Server parcourt la liste de haut en bas.

12. L’option **Activer l’accrochage RTP** doit être sélectionnée pour activer la déviation du trafic multimédia pour les clients situés derrière un pare-feu ou un convertisseur d’adresses réseau et un contrôleur SBC qui prend en charge l’accrochage.

13. L’option **Activer l’historique du transfert d’appel** doit être sélectionnée pour permettre l’envoi des informations d’historique d’appel à l’homologue de passerelle du serveur de médiation.

14. L’option **Activer les données de transfert P-Asserted-Identity** doit être sélectionnée pour autoriser le transfert des informations de l’appelant PAI (P-Asserted-Identity) entre le côté serveur de médiation et le côté passerelle (et inversement), le cas échéant.

15. L’option **Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionnée pour permettre un basculement rapide. La passerelle associée à cette jonction peut avertir dans les 10 secondes du traitement de l’appel sortant. La redirection vers une autre jonction se produit si cette notification n’est pas reçue par le serveur de médiation. Sur les réseaux dont la latence peut retarder le temps de réponse ou si la passerelle prend plus de 10 secondes à répondre, le basculement rapide doit être désactivé.

16. (Facultatif) Associez et configurez les **règles de conversion du numéro d’appel** pour la jonction. Ces règles de conversion s’appliquent au numéro appelant pour les appels sortants
    
      - Pour choisir une ou plusieurs règles dans la liste de toutes les règles de conversion disponibles dans votre déploiement de Voix Entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    
      - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour modifier une règle de conversion déjà associée à la jonction, cliquez sur le nom de la règle, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, cliquez sur le nom de la règle, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Pour supprimer une règle de conversion de la jonction, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer**.
    
    > [!WARNING]  
    > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.

17. (Facultatif) Associez et configurez les **règles de conversion de numéro appelé** pour la jonction. Les règles de conversion s’appliquent au numéro appelé dans un appel sortant.
    
      - Pour choisir une ou plusieurs règles dans la liste de toutes les règles de conversion disponibles dans votre déploiement de Voix Entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    
      - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour modifier une règle de conversion déjà associée à la jonction, cliquez sur le nom de la règle, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, cliquez sur le nom de la règle, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Pour supprimer une règle de conversion de la jonction, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer**.
    
    > [!WARNING]  
    > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.

18. Vérifiez que les règles de conversion s’affichent dans l’ordre adéquat. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!IMPORTANT]  
    > Lync Server 2013 lit la liste de règles de conversion de haut en bas et applique la première règle qui correspond au numéro composé. Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de conversion, vérifiez que les règles les plus restrictives s’affichent avant les règles les moins restrictives. Par exemple, si une règle de conversion s’applique à tout numéro à 11 chiffres et une autre s’applique à tout numéro à 11 chiffres commençant par +1425, vérifiez que la règle qui s’applique à tout numéro à 11 chiffres s’affiche <em>après</em> la règle la plus restrictive.

19. Lorsque vous avez terminé de configurer la jonction, cliquez sur **OK**.

20. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    > [!NOTE]  
    > À chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande <strong>Valider tout</strong> pour publier la modification de la configuration. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</a> dans la documentation des opérations.

Après avoir configuré la jonction, poursuivez la configuration du contournement en effectuant des sélections parmi les options globales de déviation du trafic multimédia, tel que décrit dans la section [Options globales du contournement de média dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md) de la documentation de déploiement.

## Voir aussi

#### Tâches

[Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  

#### Concepts

[Configuration de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Options globales du contournement de média dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  

#### Autres ressources

[Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md)

