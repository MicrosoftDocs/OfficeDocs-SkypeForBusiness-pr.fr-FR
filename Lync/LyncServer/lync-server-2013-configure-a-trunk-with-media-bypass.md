---
title: 'Lync Server 2013: configuration d’une Trunk avec dérivation multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trunk with media bypass
ms:assetid: 99d729ea-5a4c-4ff2-a4a3-93a24368da6d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398792(v=OCS.15)
ms:contentKeyID: 48184959
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41f5f254dfd3ad63d3f6390f16837c777bd02a91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-with-media-bypass-in-lync-server-2013"></a>Configure a trunk with media bypass in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-02-07_

Pour configurer une jonction avec l’option de déviation du trafic multimédia activée, procédez comme suit. Pour configurer un Trunk with Media Bypass Disabled, voir [configurer un Trunk sans dérivation multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md). La dérivation de média est utile lorsque vous voulez réduire le nombre de serveurs de médiation déployés. En règle générale, un pool de serveurs de médiation est déployé sur un site central et contrôle les passerelles dans les sites de succursales. L’activation de la déviation du trafic multimédia permet aux médias de passer des appels PSTN (réseau téléphonique commuté) depuis des clients situés sur les sites de succursale directement par les passerelles de ces sites. Les itinéraires d’appels sortants de Lync Server 2013 et les stratégies voix entreprise doivent être correctement configurés pour que les appels RTC de clients sur un site de succursale soient routés vers la passerelle appropriée.

Nous vous conseillons vivement d’activer la déviation du trafic multimédia. Cependant, avant de l’activer sur une jonction SIP (Session Initiation Protocol), assurez-vous que votre fournisseur de jonctions SIP compétent prend en charge cette option et qu’il peut satisfaire aux exigences d’activation du scénario. Plus spécifiquement, le fournisseur doit disposer des adresses IP des serveurs sur le réseau interne de votre organisation. Si le fournisseur ne peut pas prendre en charge ce scénario, la contournement de média ne fonctionnera pas. Pour plus d’informations, reportez-vous à la section [planification de la dérivation multimédia dans Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) dans la documentation de planification.

<div>


> [!NOTE]  
> La dérivation multimédia n’interagit pas avec chaque passerelle réseau téléphonique commuté (RTC), PBX IP et contrôleur de bordure de session (SBC). Microsoft a testé plusieurs passerelles RTC et contrôleurs SBC en collaboration avec des partenaires agréés et a effectué différents tests avec les systèmes IP-PBX de Cisco. La dérivation de média est uniquement prise en charge avec les produits et versions qui sont répertoriés dans le programme d’interopérabilité des communications unifiées-Lync Server à <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.



</div>

Une configuration de jonction, décrite ci-dessous, regroupe un ensemble de paramètres appliqués aux jonctions auxquelles cette configuration de jonction est affectée. Une configuration de jonction spécifique peut posséder une étendue globale (applicable à toutes les jonctions qui ne disposent pas d’une configuration de pool ou de site plus spécifique) ou une étendue Site ou Pool. La configuration de jonction au niveau du pool sert à appliquer une configuration de jonction spécifique à une jonction unique.

<span id="BKMK_ConfigTrunkMediaBypassSteps"></span>

<div>

## <a name="to-configure-a-trunk-with-media-bypass"></a>Pour configurer une jonction avec la déviation du trafic multimédia

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.

4.  Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :
    
      - Double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.
    
      - Cliquez sur **Nouvelle**, puis sélectionnez une étendue pour la nouvelle configuration de jonction :
        
          - **Trunk de site:** Choisissez le site pour cette configuration de Trunk dans **Sélectionner un site**, puis cliquez sur **OK**. Notez que si une configuration de Trunk a déjà été créée pour un site, ce site n’apparaît pas dans **Sélectionner un site**. Cette configuration de Trunk est appliquée à tous les Trunks du site.
        
          - **Trunk de réserve:** Sélectionnez le nom du Trunk auquel cette configuration de Trunk s’applique. Ce Trunk peut être le Trunk racine ou d’éventuelles liaisons supplémentaires définies dans le générateur de topologie. Dans **Sélectionner un service**, cliquez sur **OK**. Notez que si une configuration de Trunk a déjà été créée pour une ligne particulière, le Trunk n’apparaît pas dans **Sélectionner un service**.
    
    <div>
    

    > [!NOTE]  
    > Une fois que l’étendue de la configuration de jonction est sélectionnée, elle ne peut plus être modifiée.<BR>Le champ <STRONG>Nom</STRONG> est prérempli et comporte le nom du site ou du service associé à la configuration de jonction. Ce nom ne peut pas être modifié.

    
    </div>

5.  Spécifiez une valeur dans **Nombre maximal de boîtes de dialogue anticipées prises en charge**. Il s’agit du nombre maximal de réponses dirigées qu’une passerelle RTC, IP-PBX ou qu’un contrôleur SBC (Session Border Controller) d’un fournisseur de services de téléphonie et Internet (ITSP) peut recevoir à une INVITATION envoyée au serveur de médiation. La valeur par défaut est 20.
    
    <div>
    

    > [!NOTE]  
    > Avant de modifier cette valeur, consultez votre fournisseur de services ou le fabricant de matériel pour plus d’informations sur les capacités de votre système.

    
    </div>

6.  Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement** :
    
      - **Obligatoire:** Le chiffrement SRTP (Secure Real-Time Transport Protocol) doit être utilisé pour protéger le trafic entre le serveur de médiation et la passerelle ou le PBX (Private Branch Exchange).
    
      - **Facultatif:** Le chiffrement SRTP est utilisé si le prestataire de services ou le fabricant du matériel le prend en charge.
    
      - **Non pris en charge:** Le chiffrement SRTP n’est pas pris en charge par le fabricant du fournisseur de services ou de l’équipement et ne sera donc pas utilisé.

7.  Activez la case à cocher **Activer la déviation du trafic multimédia** si vous souhaitez que le trafic multimédia contourne le serveur de médiation pour être traité par l’homologue de jonction.
    
    <div>
    

    > [!IMPORTANT]  
    > Pour que la déviation du trafic multimédia fonctionne correctement, la passerelle RTC, un IP-PBX ou un contrôleur SBC ITSP doit prendre en charge certaines fonctionnalités. Pour plus d’informations, reportez-vous à la section <A href="lync-server-2013-planning-for-media-bypass.md">planification de la dérivation multimédia dans Lync Server 2013</A> dans la documentation de planification.

    
    </div>

8.  Activez la case à cocher **Traitement multimédia centralisé** s’il existe un point de terminaison multimédia connu (par exemple, une passerelle RTC où la terminaison multimédia possède la même adresse IP que la terminaison de signalisation). Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.

9.  Si l’homologue de Trunk prend en charge la réception des demandes de renvoi SIP du serveur de médiation, activez la case à cocher **activer l’envoi** .
    
    <div>
    

    > [!NOTE]  
    > Si vous désactivez cette option alors que l’option <STRONG>Activer la déviation du trafic multimédia</STRONG> est sélectionnée, des paramètres supplémentaires sont requis. Si l’homologue de jonction ne prend pas en charge la réception des requêtes SIP (Session Initiation Protocol) REFER du serveur de médiation et si la déviation du trafic multimédia est activée, vous devez également exécuter l’applet de commande <STRONG>Set-CsTrunkConfiguration</STRONG> pour désactiver le RTCP pour les appels en cours ou en attente afin de prendre en charge les conditions appropriées à la déviation du trafic multimédia. Pour plus d’informations, consultez la documentation de <A href="lync-server-2013-lync-server-management-shell.md">Lync Server 2013 Management Shell</A> .<BR>En guise d’alternative, vous pouvez sélectionner <STRONG>Activer la référence avec un contrôle d’appel tiers</STRONG> si vous souhaitez que les appels transférés soient soumis à la déviation du trafic multimédia et que la passerelle ne prend pas en charge les demandes SIP (Session Initiation Protocol) REFER.

    
    </div>

10. (Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation RTC à cette configuration de jonction. Les utilisations RTC associées à cette configuration de Trunk s’appliquent à tous les appels entrants par le biais du Trunk qui n’est pas provenant d’un point de terminaison Lync. Pour gérer les enregistrements d’utilisation RTC associés à une configuration de jonction, appliquez l’une des méthodes suivantes :
    
      - Pour sélectionner un ou plusieurs enregistrements dans la liste de tous les enregistrements d’utilisation RTC disponibles dans le déploiement de votre voix entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette configuration de jonction, puis cliquez sur **OK**.
    
      - Pour supprimer un enregistrement d’utilisation RTC de cette configuration de jonction, sélectionnez l’enregistrement, puis cliquez sur **Supprimer**.
    
      - Pour définir un nouvel enregistrement d’utilisation RTC et l’associer à cette configuration de jonction, procédez comme suit :
        
        1.  Cliquez sur **Nouveau**.
        
        2.  Dans le champ **Nom**, indiquez un nom descriptif unique pour l’enregistrement.
            
            <div>
            

            > [!NOTE]  
            > Le nom de l’enregistrement d’utilisation RTC doit être unique dans le déploiement Voix Entreprise. Une fois que vous avez enregistré l’enregistrement, vous ne pouvez plus modifier le champ <STRONG>Nom</STRONG>.

            
            </div>
        
        3.  Pour associer et configurer les itinéraires pour cet enregistrement d’utilisation RTC, appliquez l’une des méthodes suivantes :
            
              - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans le déploiement de votre voix entreprise, cliquez sur **Sélectionner**. Sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.
            
              - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            
              - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, reportez-vous à [créer un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Pour modifier un itinéraire associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, voir [modifier un itinéraire vocal dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Cliquez sur **OK**.
    
      - Pour modifier un enregistrement d’utilisation RTC déjà associé à cette configuration de jonction, procédez comme suit :
        
        1.  Sélectionnez l’enregistrement d’utilisation RTC à modifier, puis cliquez sur **Afficher les détails**.
        
        2.  Pour associer et configurer les itinéraires pour cet enregistrement d’utilisation RTC, appliquez l’une des méthodes suivantes :
            
              - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans le déploiement de votre voix entreprise, cliquez sur **Sélectionner**. Sélectionnez les itinéraires à associer à cet enregistrement d’utilisation RTC, puis cliquez sur **OK**.
            
              - Pour supprimer un itinéraire de l’enregistrement d’utilisation RTC, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            
              - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation RTC, cliquez sur **Nouveau**. Pour plus d’informations, reportez-vous à [créer un itinéraire vocal dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Pour modifier un itinéraire associé à cet enregistrement d’utilisation RTC, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, voir [modifier un itinéraire vocal dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Cliquez sur **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > Il est important d’associer les enregistrements d’utilisation RTC en fonction de l’homologue du serveur de médiation associé au Trunk en cours de configuration. S’il s’agit d’une passerelle PSTN ou d’un contrôleur de bordure de session (SBC), il est vivement recommandé que la configuration de Trunk ne soit pas associée à un enregistrement d’utilisation RTC qui achemine vers une destination PSTN ou tout autre système en aval connecté via Lync. Serveurs.

    
    </div>

11. Organisez les enregistrements d’utilisation RTC pour bénéficier de performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation RTC, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    <div>
    

    > [!IMPORTANT]  
    > L’ordre des enregistrements d’utilisation RTC dans la liste de la configuration de jonction a son importance. Lync Server parcourt la liste de haut en bas.

    
    </div>

12. L’option **Activer l’accrochage RTP** doit être sélectionnée pour activer la déviation du trafic multimédia pour les clients situés derrière un pare-feu ou un convertisseur d’adresses réseau (NAT) et un contrôleur SBC qui prend en charge l’accrochage.

13. L’option **activer l’historique des appels en aval** doit être sélectionnée pour permettre l’envoi des informations de l’historique des appels à l’homologue de la passerelle du serveur de médiation.

14. **Activez le transfert des données d’identité p-assertion** qui doivent être sélectionnées pour permettre aux informations de l’appelant d’appeler p-assertion (PAI) d’être transmises entre le côté du serveur de médiation et le côté passerelle (et vice versa), le cas échéant.

15. L’option **Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionnée pour permettre un basculement rapide. La passerelle associée à cette jonction peut avertir dans les 10 secondes du traitement de l’appel sortant. Le reroutage vers un autre Trunk se produit si la notification n’est pas reçue par le serveur de médiation. Sur les réseaux dont la latence peut retarder le temps de réponse ou si la passerelle met plus de 10 secondes à répondre, le basculement rapide doit être désactivé.

16. (Facultatif) Associez et configurez les **règles de conversion du numéro d’appel** pour la jonction. Ces règles de conversion s’appliquent au numéro appelant pour les appels sortants
    
      - Pour sélectionner une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    
      - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une règle, voir [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour modifier une règle de conversion déjà associée à la jonction, sélectionnez le nom de la règle, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.
    
    <div>
    

    > [!WARNING]  
    > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.

    
    </div>

17. (Facultatif) Associez et configurez les **règles de conversion de numéro appelé** pour la jonction. Les règles de conversion s’appliquent au numéro appelé dans un appel sortant.
    
      - Pour sélectionner une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    
      - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une règle, voir [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour modifier une règle de conversion déjà associée à la jonction, sélectionnez le nom de la règle, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.
    
    <div>
    

    > [!WARNING]  
    > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.

    
    </div>

18. Vérifiez que les règles de conversion s’affichent dans l’ordre adéquat. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server 2013 parcourt la liste des règles de traduction du haut vers le bas et utilise la première règle correspondant au numéro numéroté. Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de conversion, vérifiez que les règles les plus restrictives s’affichent avant les règles les moins restrictives. Par exemple, si une règle de conversion s’applique à tout numéro à 11 chiffres et qu’une autre s’applique à tout numéro à 11 chiffres commençant par +1425, vérifiez que la règle qui s’applique à tout numéro à 11 chiffres s’affiche <EM>après</EM> la règle la plus restrictive.

    
    </div>

19. Lorsque vous avez fini de configurer la jonction, cliquez sur **OK**.

20. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Tout valider**.
    
    <div>
    

    > [!NOTE]  
    > Chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande <STRONG>Tout valider</STRONG> pour publier la modification de la configuration. Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation

    
    </div>

Après avoir configuré le Trunk, continuez à configurer le contournement multimédia en choisissant entre les options de contournement globales du média, comme décrit dans la section [options de contournement global de médias de Lync Server 2013](lync-server-2013-global-media-bypass-options.md) dans la documentation de déploiement.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configurer un Trunk sans dérivation multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-without-media-bypass.md)  


[Configuration de la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-media-bypass.md)  
[Options de contournement global de médias dans Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  


[Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

