---
title: 'Lync Server 2013 : configuration d’une jonction sans déviation du trafic multimédia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure a trunk without media bypass
ms:assetid: 3422e93e-7bd2-4470-968c-dc38345b18ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425831(v=OCS.15)
ms:contentKeyID: 48183825
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e3b8f0c14ca916c7a4920a4399df441fb61bc48
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146607"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-a-trunk-without-media-bypass-in-lync-server-2013"></a>Configuration d’une jonction sans déviation du trafic multimédia dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-24_

Pour configurer une jonction sur laquelle le contournement de média est désactivé, procédez comme suit. Si vous souhaitez configurer une jonction avec la déviation du trafic multimédia activée, consultez [la rubrique Configure a trunk with Media Bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).

Une configuration de jonction, comme décrit plus bas, regroupe un ensemble de paramètres appliqués aux jonctions affectées à cette configuration de jonction. Une configuration de jonction spécifique peut s’étendre au niveau global (à toutes les jonctions qui ne disposent plus d’une configuration de site ou de pool spécifique) ou au niveau d’un site ou d’un pool. La configuration de jonction au niveau du pool est utilisée pour étendre une configuration de jonction spécifique à une jonction unique.

<span id="BKMK_ConfigTrunkGenericSteps"></span>

<div>

## <a name="to-configure-a-trunk-without-media-bypass"></a>Pour configurer une jonction sans contournement de média

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Configuration de la jonction**.

4.  Dans la page **Configuration de la jonction**, configurez une jonction à l’aide de l’une des méthodes suivantes :
    
      - Double-cliquez sur une jonction existante (par exemple, la jonction **Global**) pour afficher la boîte de dialogue **Modifier la configuration de la jonction**.
    
      - Cliquez sur **Nouvelle**, puis sélectionnez l’étendue de la nouvelle configuration de jonction :
        
          - **Jonction de site :** Choisissez le site pour cette configuration de jonction dans **Sélectionner un site** , puis cliquez sur **OK**. Notez que si une configuration de jonction a déjà été créée pour un site, le site ne s’affiche pas dans **Sélectionner un site**. Cette configuration de jonction sera appliquée à toutes les jonctions du site.
        
          - **Jonction de pool :** Choisissez le nom de la jonction à laquelle s’applique cette configuration de jonction dans **Sélectionner un service** , puis cliquez sur **OK**. Cette jonction peut être la jonction racine ou toute autre jonction définie dans le générateur de topologie. Notez que si une configuration de jonction a déjà été créée pour une jonction spécifique, la jonction ne s’affiche pas dans **Sélectionner un service**.
    
    <div>
    

    > [!NOTE]  
    > Une fois que vous avez sélectionné l’étendue de la configuration de jonction, elle n’est plus modifiable.<BR>Le champ <STRONG>Nom</STRONG> est prérempli et comporte le nom du site ou service associé à la configuration de jonction. Ce nom n’est pas modifiable.

    
    </div>

5.  Sélectionnez l’une des options de **Niveau de prise en charge du chiffrement** :
    
      - **Obligatoire :** Le chiffrement SRTP (Secure Real-Time Transport Protocol) doit être utilisé pour protéger le trafic entre le serveur de médiation et la passerelle ou le système PBX (Private Branch Exchange).
    
      - **Facultatif :** Le chiffrement SRTP sera utilisé s’il est pris en charge par le fournisseur de services ou le fabricant.
    
      - **Non pris en charge :** Le chiffrement SRTP n’est pas pris en charge par le fournisseur de services ou le fabricant de l’équipement et ne sera donc pas utilisé.

6.  Assurez-vous que la case à cocher **Activer le contournement de média** est désactivée.

7.  Activez la case à cocher **Traitement multimédia centralisé** si un point de terminaison média connu existe (par exemple, une passerelle PSTN sur laquelle la terminaison multimédia possède la même adresse IP que la terminaison de signalisation). Désactivez cette case à cocher si la jonction ne comporte pas de point de terminaison multimédia connu.

8.  Si l’homologue de jonction prend en charge la réception des demandes SIP REFER à partir du serveur de médiation, activez la case à cocher **activer l’envoi en tant que passerelle** .

9.  (Facultatif) Pour permettre le routage interjonction, associez et configurez les enregistrements d’utilisation PSTN à la configuration de cette jonction. Les utilisations PSTN associées à cette configuration de jonction seront appliquées à tous les appels entrants via la jonction qui ne provient pas d’un point de terminaison Lync. Pour gérer les enregistrements d’utilisation PSTN associés à une configuration de jonction, utilisez l’une des méthodes suivantes :
    
      - Pour sélectionner un ou plusieurs enregistrements dans la liste de tous les enregistrements d’utilisation RTC disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette configuration de jonction, puis cliquez sur **OK**.
    
      - Pour supprimer un enregistrement d’utilisation PSTN de cette configuration de jonction, sélectionnez l’enregistrement, puis cliquez sur **Supprimer**.
    
      - Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette configuration de jonction, procédez comme suit :
        
        1.  Cliquez sur **Nouveau**.
        
        2.  Dans le champ **Nom**, indiquez un nom descriptif unique pour l’enregistrement.
            
            <div>
            

            > [!NOTE]  
            > Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ <STRONG>Nom</STRONG> ne peut plus être modifié.

            
            </div>
        
        3.  Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation PSTN :
            
              - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.
            
              - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            
              - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Pour modifier un itinéraire associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Cliquez sur **OK**.
    
      - Pour modifier un enregistrement d’utilisation PSTN déjà associé à cette configuration de jonction, procédez comme suit :
        
        1.  Sélectionnez l’enregistrement d’utilisation PSTN que vous voulez modifier, puis cliquez sur **Afficher les détails**.
        
        2.  Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires pour cet enregistrement d’utilisation PSTN :
            
              - Pour sélectionner un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.
            
              - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire et cliquez sur **Supprimer**.
            
              - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Pour modifier un itinéraire associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Cliquez sur **OK**.
    
    <div>
    

    > [!IMPORTANT]  
    > Il est important d’associer les enregistrements d’utilisation PSTN en fonction de l’homologue de serveur de médiation associé à la jonction en cours de configuration. Si l’homologue du serveur de médiation est une passerelle RTC ou un contrôleur de frontière de session (SBC), il est vivement recommandé que la configuration de jonction ne soit pas associée à un enregistrement d’utilisation PSTN qui achemine vers une destination PSTN ou tout autre système en aval connecté via Lync. Serveurs.

    
    </div>

10. Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez l’enregistrement d’utilisation PSTN, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    <div>
    

    > [!IMPORTANT]  
    > L’ordre des enregistrements d’utilisation PSTN dans la liste de la configuration de jonction a son importance. Lync Server parcourt la liste de haut en bas.

    
    </div>

11. **Activer l’accrochage RTP** doit être sélectionné pour activer la déviation du trafic multimédia pour les clients se trouvant derrière une NAT ou un pare-feu et un contrôleur SBC prenant en charge l’accrochage.

12. **Activer l’historique du transfert d’appel** doit être sélectionné pour permettre l’envoi des informations d’historique d’appel à l’homologue de passerelle du serveur de médiation.

13. **Activation des données de transfert P-asserted-Identity** doivent être sélectionnées pour permettre le transfert des informations de l’expéditeur de l’appel PAI entre le côté serveur de médiation et la passerelle (et vice versa), le cas échéant.

14. **Activer le minuteur de basculement de routage de trafic sortant** doit être sélectionné pour permettre un basculement rapide. La passerelle associée à cette jonction peut informer dans les 10 secondes du traitement de l’appel sortant. La redirection vers une autre jonction se produira si cette notification n’est pas reçue par le serveur de médiation. Sur des réseaux avec une latence qui peut retarder le temps de réponse ou si la passerelle prend plus de 10 secondes à répondre, le basculement rapide doit être désactivé.

15. (Facultatif) Associez et configurez les **règles de traduction du numéro d’appel** pour la jonction. Ces règles de traduction s’appliquent au numéro appelant pour les appels sortants
    
      - Pour choisir une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de traduction**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    
      - Si vous voulez définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.
    
    <div>
    
    <table>
    <thead>
    <tr class="header">
    <th><img src="images/Gg398321.security(OCS.15).gif" title="caution" alt="security" />Note de sécurité :</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td>N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit.</td>
    </tr>
    </tbody>
    </table>
    
    </div>

16. (Facultatif) Associez et configurez les **règles de traduction de numéro appelé** pour la jonction. Les règles de traduction s’appliquent au numéro appelé dans un appel sortant.
    
      - Pour choisir une ou plusieurs règles dans la liste de toutes les règles de traduction disponibles dans votre déploiement voix entreprise, cliquez sur **Sélectionner**. Dans **Sélectionner les règles de traduction**, cliquez sur les règles à associer à la jonction, puis cliquez sur **OK**.
    
      - Si vous voulez définir une nouvelle règle de traduction et l’associer à la jonction, cliquez sur **Nouvelle**. Pour plus d’informations sur la définition d’une nouvelle règle, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour modifier une règle de traduction associée à une jonction, cliquez sur son nom, puis sur **Afficher les détails**. Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md) dans la documentation de déploiement.
    
      - Pour copier une règle de traduction existante qui servira de point de départ à la définition d’une nouvelle règle, cliquez sur son nom, sur **Copier**, puis sur **Coller**. Pour plus d’informations, reportez-vous à la rubrique [définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md).
    
      - Pour supprimer une règle de traduction d’une jonction, sélectionnez son nom, puis cliquez sur **Supprimer**.
    
    <div>
    

    > [!WARNING]  
    > N’associez pas de règles de traduction à une configuration de jonction si vous avez configuré les règles de traduction sur l’homologue de jonction associé, car les deux règles risqueraient d’entrer en conflit.

    
    </div>

17. Assurez-vous que les règles de traduction de la jonction sont organisées dans le bon ordre. Pour déplacer une règle dans la liste, sélectionnez-la, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    <div>
    

    > [!IMPORTANT]  
    > Lync Server parcourt la liste de règles de traduction du haut vers le bas et utilise la première règle qui correspond au numéro composé. Si vous configurez une jonction de sorte qu’un numéro composé corresponde à plusieurs règles de traduction, assurez-vous que les règles les plus restrictives apparaissent avant les règles les moins restrictives. Par exemple, si une règle de traduction s’applique à tout numéro à 11 chiffres et une autre s’applique à tout numéro à 11 chiffres commençant par +1425, assurez-vous que la règle qui s’applique à tout numéro à 11 chiffres apparaît <EM>après</EM> la règle la plus restrictive.

    
    </div>

18. Lorsque vous avez terminé de configurer la jonction, cliquez sur **OK**.

19. Dans la page **Configuration de la jonction**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    <div>
    

    > [!NOTE]  
    > À chaque fois que vous créez ou modifiez une configuration de jonction, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.

    
    </div>

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration d’une jonction avec la déviation du trafic multimédia dans Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Définition de règles de conversion dans Lync Server 2013](lync-server-2013-defining-translation-rules.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

