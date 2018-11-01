---
title: "Lync Server 2013 : Conf. d’une jonction sans déviation du trafic multimédia"
TOCTitle: Configuration d’une jonction sans déviation du trafic multimédia
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg425831(v=OCS.15)
ms:contentKeyID: 49296815
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2013-02-24_

Pour configurer une jonction sur laquelle la déviation du trafic multimédia est désactivée, procédez comme suit. Pour configurer une jonction sur laquelle cette fonctionnalité est activée, reportez-vous à [Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

Une configuration de jonction, comme décrit plus bas, regroupe un ensemble de paramètres appliqués aux jonctions affectées à cette configuration de jonction. Une configuration de jonction spécifique peut s’étendre au niveau global (à toutes les jonctions qui ne disposent plus d’une configuration de site ou de pool spécifique) ou au niveau d’un site ou d’un pool. La configuration de jonction au niveau du pool est utilisée pour étendre une configuration de jonction spécifique à une jonction unique.

## Pour configurer une jonction sans déviation du trafic multimédia

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, voir [Délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes de démarrage du Panneau de configuration Lync Server, voir [Ouvrir les outils d’administration Lync Server](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.

4.  Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :
    
      - Double-cliquez sur une jonction existante (par exemple, la jonction **Global** ) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.
    
      - Cliquez sur **Nouvelle**, puis sélectionnez une étendue pour la nouvelle configuration de jonction :
        
          - **Jonction de site** : choisissez le site de la configuration de jonction dans **Sélectionner un site**, puis cliquez sur **OK**. Notez que si une jonction a déjà été créée pour un site, le site ne s’affiche pas dans **Sélectionner un site**. Cette configuration de jonction sera appliquée à toutes les jonctions du site.
        
          - **Jonction de pool** : choisissez le nom de la jonction à laquelle s’applique cette configuration de jonction dans **Sélectionner un service**, puis cliquez sur **OK**. Cette jonction peut être la jonction racine ou toutes autres jonctions définies dans le Générateur de topologie. Notez que si une configuration de jonction a déjà été créée pour une jonction spécifique, la jonction ne s’affiche pas dans **Sélectionner un service**.
    
    > [!NOTE]  
    > Une fois que vous avez sélectionné l’étendue de la configuration de jonction, elle n’est plus modifiable.<br />
    Le champ <strong>Nom</strong> est prérempli et comporte le nom du site ou service associé à la configuration de jonction. Ce nom n’est pas modifiable.

5.  Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement**  :
    
      - **Requis** : le chiffrement SRTP (Secure Real-time Transport Protocol) doit être utilisé pour aider à protéger le trafic entre le serveur de médiation et la passerelle ou le système PBX (Private Branch Exchange).
    
      - **Facultatif** : le chiffrement SRTP sera utilisé s’il est pris en charge par le fournisseur de services ou le fabricant.
    
      - **Non pris en charge** : le chiffrement SRTP n’étant pas pris en charge pas le fournisseur de services ou le fabricant, il ne peut pas être utilisé.

6.  Assurez-vous que la case à cocher **Activer la déviation du trafic multimédia** est désactivée.

7.  Activez la case à cocher **Traitement multimédia centralisé** si un point de terminaison média connu existe (par exemple, une passerelle RTC sur laquelle la terminaison multimédia possède la même adresse IP que la terminaison de signalisation). Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.

8.  Si l’homologue de jonction prend en charge la réception les demandes SIP REFER provenant du serveur de médiation, activez la case à cocher **Activer la référence d’appel vers la passerelle**.

9.  (Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation RTC à cette configuration de jonction. Les utilisations RTC associées à cette configuration de jonction seront appliquées à tous les appels entrants via la jonction qui ne provient pas d’un point de terminaison Lync. Pour gérer les enregistrements d’utilisation RTC associés à une configuration de jonction, appliquez l’une des méthodes suivantes :
    
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

10. Organisez les enregistrements d’utilisation RTC pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation RTC, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!IMPORTANT]  
    > L’ordre des enregistrements d’utilisation RTC dans la liste de la configuration de jonction a son importance. Lync Server parcourt la liste de haut en bas.

11. **Activer l’accrochage RTP** doit être sélectionné pour activer la déviation du trafic multimédia pour les clients se trouvant derrière une NAT ou un pare-feu et un contrôleur SBC prenant en charge l’accrochage.

12. L’option **Activer l’historique du transfert d’appel** doit être sélectionnée pour permettre l’envoi des informations d’historique d’appel à l’homologue de passerelle du serveur de médiation.

13. **Activer les données de transfert P-Asserted-Identity** doit être sélectionné pour activer les informations de PAI de l’appelant à transférer entre le serveur de médiation et la passerelle (et inversement), le cas échéant.

14. L’option **Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionnée pour permettre un basculement rapide. La passerelle associée à cette jonction peut avertir dans les 10 secondes du traitement de l’appel sortant. La redirection vers une autre jonction se produit si cette notification n’est pas reçue par le serveur de médiation. Sur les réseaux dont la latence peut retarder le temps de réponse ou si la passerelle prend plus de 10 secondes à répondre, le basculement rapide doit être désactivé.

15. (Facultatif) Associez et configurez les **règles de conversion du numéro d’appel** pour la jonction. Ces règles de conversion s’appliquent au numéro appelant pour les appels sortants
    
      - Pour choisir une ou plusieurs règles dans la liste de toutes les règles de conversion disponibles dans votre déploiement de Voix Entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    
      - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour modifier une règle de conversion déjà associée à la jonction, cliquez sur le nom de la règle, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, cliquez sur le nom de la règle, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Pour supprimer une règle de conversion de la jonction, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer**.
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="security" alt="security" />Sécurité Remarque :</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.</td>
    </tr>
    </tbody>
    </table>

16. (Facultatif) Associez et configurez les **règles de conversion de numéro appelé** pour la jonction. Les règles de conversion s’appliquent au numéro appelé dans un appel sortant.
    
      - Pour choisir une ou plusieurs règles dans la liste de toutes les règles de conversion disponibles dans votre déploiement de Voix Entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    
      - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour modifier une règle de conversion déjà associée à la jonction, cliquez sur le nom de la règle, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, cliquez sur le nom de la règle, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à [Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Pour supprimer une règle de conversion de la jonction, mettez en surbrillance le nom de la règle et cliquez sur **Supprimer**.
    
    > [!CAUTION]  
    > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.

17. Vérifiez que les règles de conversion s’affichent dans l’ordre adéquat. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    > [!IMPORTANT]  
    > Lync Server lit la liste de règles de conversion de haut en bas et applique la première règle qui correspond au numéro composé. Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de conversion, vérifiez que les règles les plus restrictives s’affichent avant les règles les moins restrictives. Par exemple, si une règle de conversion s’applique à tout numéro à 11 chiffres et une autre à tout numéro à 11 chiffres commençant par +1425, assurez-vous que la règle s’appliquant à tout numéro à 11 chiffres s’affiche <em>après</em> la règle la plus restrictive.

18. Lorsque vous avez terminé de configurer la jonction, cliquez sur **OK**.

19. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    > [!NOTE]  
    > À chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande <strong>Valider tout</strong> pour publier la modification de la configuration. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">Publication des modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013</a> dans la documentation des opérations.

## Voir aussi

#### Tâches

[Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  

#### Autres ressources

[Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md)

