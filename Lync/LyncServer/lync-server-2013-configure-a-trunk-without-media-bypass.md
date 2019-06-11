---
title: 'Lync Server 2013: configurer un Trunk sans dérivation multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e6508fe88a585c22b9936e787be2ee99b8f9b7c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838479"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a>Configurer un Trunk sans dérivation multimédia dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-24_

Pour configurer une jonction sur laquelle la déviation du trafic multimédia est désactivée, procédez comme suit. Si vous voulez configurer un Trunk avec une dérivation multimédia activée, voir [configurer une Trunk with Media bypass dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

Une configuration de jonction, comme indiqué dans la suite de cette rubrique, regroupe un ensemble de paramètres appliqués aux jonctions affectées à cette configuration de jonction. Une configuration de jonction spécifique peut s’étendre au niveau global (à toutes les jonctions qui ne disposent plus d’une configuration de site ou de pool spécifique) ou au niveau d’un site ou d’un pool. La configuration de jonction au niveau du pool est utilisée pour étendre une configuration de jonction spécifique à une jonction unique.

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a>Pour configurer une jonction sans déviation du trafic multimédia

1.  Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou en tant que membre du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la section [délégation des autorisations de configuration dans Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.

4.  Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :
    
      - Double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.
    
      - Cliquez sur **Nouvelle**, puis sélectionnez une étendue pour la nouvelle configuration de jonction :
        
          - **Trunk de site:** Choisissez le site pour cette configuration de Trunk dans **Sélectionner un site** , puis cliquez sur **OK**. Notez que si une configuration de Trunk a déjà été créée pour un site, ce site n’apparaît pas dans **Sélectionner un site**. Cette configuration de Trunk est appliquée à tous les Trunks du site.
        
          - **Trunk de réserve:** Sélectionnez le nom du Trunk auquel s’applique cette configuration de Trunk dans **Sélectionner un service** , puis cliquez sur **OK**. Ce Trunk peut être le Trunk racine ou d’éventuelles liaisons supplémentaires définies dans le générateur de topologie. Notez que si une configuration de Trunk a déjà été créée pour une ligne particulière, le Trunk n’apparaît pas dans **Sélectionner un service**.
    
    <div>
    

    > [!NOTE]  
    > Une fois que l’étendue de la configuration de jonction est sélectionnée, elle ne peut plus être modifiée.<BR>Le champ <STRONG>Nom</STRONG> est prérempli et comporte le nom du site ou du service associé à la configuration de jonction. Ce nom ne peut pas être modifié.

    
    </div>

5.  Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement** :
    
      - **Obligatoire:** Le chiffrement SRTP (Secure Real-Time Transport Protocol) doit être utilisé pour protéger le trafic entre le serveur de médiation et la passerelle ou le PBX (Private Branch Exchange).
    
      - **Facultatif:** Le chiffrement SRTP est utilisé si le prestataire de services ou le fabricant du matériel le prend en charge.
    
      - **Non pris en charge:** Le chiffrement SRTP n’est pas pris en charge par le fabricant du fournisseur de services ou de l’équipement et ne sera donc pas utilisé.

6.  Assurez-vous que la case à cocher **Activer la déviation du trafic multimédia** est désactivée.

7.  Activez la case à cocher **traitement multimédia centralisé** s’il y a un point de terminaison de média bien connu (par exemple, une passerelle RTC (réseau téléphonique commuté) pour laquelle la terminaison du signalement a la même adresse IP. Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.

8.  Si l’homologue de Trunk prend en charge la réception des demandes de renvoi SIP du serveur de médiation, activez la case à cocher **activer l’envoi** .

9.  (Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation RTC à cette configuration de jonction. Les utilisations RTC associées à cette configuration de Trunk s’appliquent à tous les appels entrants par le biais du Trunk qui n’est pas provenant d’un point de terminaison Lync. Pour gérer les enregistrements d’utilisation RTC associés à une configuration de jonction, appliquez l’une des méthodes suivantes :
    
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

10. Organisez les enregistrements d’utilisation RTC pour bénéficier de performances optimales. Pour modifier la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation RTC, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    <div>
    

    > [!IMPORTANT]  
    > L’ordre des enregistrements d’utilisation RTC dans la liste de la configuration de jonction a son importance. Lync Server parcourt la liste de haut en bas.

    
    </div>

11. **Activer l’accrochage RTP** doit être sélectionné pour activer la déviation du trafic multimédia pour les clients se trouvant derrière un convertisseur d’adresses réseau (NAT) ou un pare-feu et un contrôleur SBC prenant en charge l’accrochage.

12. L’option **activer l’historique des appels en aval** doit être sélectionnée pour permettre l’envoi des informations de l’historique des appels à l’homologue de la passerelle du serveur de médiation.

13. **Autorisez les données de renvoi d’identité P** qui doivent être sélectionnées pour permettre aux informations de l’appelant d’appeler PAI d’être transmises entre le côté du serveur de médiation et la passerelle (et vice versa), le cas échéant.

14. L’option **Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionnée pour permettre un basculement rapide. La passerelle associée à cette jonction peut avertir dans les 10 secondes du traitement de l’appel sortant. Le reroutage vers un autre Trunk se produit si la notification n’est pas reçue par le serveur de médiation. Sur les réseaux dont la latence peut retarder le temps de réponse ou si la passerelle met plus de 10 secondes à répondre, le basculement rapide doit être désactivé.

15. (Facultatif) Associez et configurez les **règles de conversion du numéro d’appel** pour la jonction. Ces règles de conversion s’appliquent au numéro appelant pour les appels sortants
    
      - Pour sélectionner une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    
      - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une règle, voir [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour modifier une règle de conversion déjà associée à la jonction, sélectionnez le nom de la règle, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="sûreté" alt="security" />Note de sécurité:</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. (Facultatif) Associez et configurez les **règles de conversion de numéro appelé** pour la jonction. Les règles de conversion s’appliquent au numéro appelé dans un appel sortant.
    
      - Pour sélectionner une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de conversion**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    
      - Pour définir une nouvelle règle de conversion et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une règle, voir [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour modifier une règle de conversion déjà associée à la jonction, sélectionnez le nom de la règle, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour copier une règle de conversion existante à utiliser comme point de départ pour définir une nouvelle règle, sélectionnez le nom de la règle, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à [définition des règles de traduction dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Pour supprimer une règle de conversion de la jonction, sélectionnez le nom de la règle et cliquez sur **Supprimer**.
    
    <div>
    

    > [!WARNING]  
    > N’associez pas de règles de conversion à une configuration de jonction si vous avez configuré les règles de conversion sur l’homologue de jonction associé, car les deux règles risquent d’entrer en conflit.

    
    </div>

17. Vérifiez que les règles de conversion s’affichent dans l’ordre adéquat. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server parcourt la liste des règles de traduction du haut vers le bas et utilise la première règle correspondant au numéro numéroté. Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de conversion, vérifiez que les règles les plus restrictives s’affichent avant les règles les moins restrictives. Par exemple, si une règle de conversion s’applique à tout numéro à 11 chiffres et qu’une autre s’applique à tout numéro à 11 chiffres commençant par +1425, vérifiez que la règle qui s’applique à tout numéro à 11 chiffres s’affiche <EM>après</EM> la règle la plus restrictive.

    
    </div>

18. Lorsque vous avez fini de configurer la jonction, cliquez sur **OK**.

19. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Tout valider**.
    
    <div>
    

    > [!NOTE]  
    > Chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande <STRONG>Tout valider</STRONG> pour publier la modification de la configuration. Pour plus d’informations, reportez-vous <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">à la rubrique publier des modifications en attente sur la configuration de l’acheminement de la voix dans Lync Server 2013</A> dans la documentation

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

