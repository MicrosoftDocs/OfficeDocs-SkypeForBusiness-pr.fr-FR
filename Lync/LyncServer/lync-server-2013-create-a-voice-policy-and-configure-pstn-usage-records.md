---
title: 'Lync Server 2013 : création d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a voice policy and configure PSTN usage records
ms:assetid: e6ff27e0-e2d1-4445-840f-08f738200c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399027(v=OCS.15)
ms:contentKeyID: 48185693
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: deaf2b1b1962e973fe84bd6db7b8b43373bfcba4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-voice-policy-and-configure-pstn-usage-records-in-lync-server-2013"></a>Création d’une stratégie de voix et configuration des enregistrements d’utilisation PSTN dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Procédez comme suit pour créer une stratégie de voix. Si vous souhaitez modifier une stratégie de voix, voir [modifier une stratégie de voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md) pour la procédure.

<div>


> [!NOTE]  
> Chaque stratégie de voix doit être associée à au moins un enregistrement d’utilisation réseau téléphonique commuté (PSTN). Pour afficher la liste de tous les enregistrements d’utilisation RTC disponibles dans votre déploiement voix entreprise et afficher leurs propriétés, voir <A href="lync-server-2013-view-pstn-usage-records.md">afficher les enregistrements d’utilisation PSTN dans Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-voice-policy"></a>Pour créer une stratégie de voix

1.  Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou du rôle CsVoiceAdministrator, CsServerAdministrator ou CsAdministrator. Pour plus d’informations, reportez-vous à la rubrique [Delegate Setup Permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**, puis sur **Stratégie de la voix**.

4.  Dans la page **Stratégie de la voix**, cliquez sur **Nouveau** puis sélectionnez l’étendue de la nouvelle stratégie :
    
      - La **stratégie de site** s’applique à l’ensemble d’un site, à l’exception des utilisateurs ou groupes attribués à une stratégie d’utilisateur. Si vous sélectionnez l’étendue Site pour une stratégie, choisissez le site dans la boîte de dialogue **Sélectionner un site**. Si une stratégie de voix a déjà été créée pour un site, le site n’apparaît pas dans la boîte de dialogue **Sélectionner un site**.
    
      - Une **stratégie d’utilisateur** peut être appliquée à des utilisateurs ou à des groupes spécifiés.

5.  Si l’étendue de la stratégie de voix est Utilisateur, entrez un nom descriptif de la stratégie dans le champ **Nom**.
    
    <div>
    

    > [!NOTE]  
    > Si l’étendue de la stratégie de voix est Site, le champ <STRONG>Nom</STRONG> de la boîte de dialogue <STRONG>Nouvelle stratégie de voix</STRONG> est prérempli avec le nom du site et ne peut pas être modifié.

    
    </div>

6.  (Optionnel) Entrez une description supplémentaire de la stratégie de voix.

7.  Activez ou désactivez les cases à cocher suivantes pour activer ou désactiver chacune des **fonctionnalités d’appel** pour cette stratégie de voix :
    
      - **Voice mail escape** empêche les appels d’être immédiatement routés vers le système de messagerie vocale du téléphone mobile de l’utilisateur lorsque la sonnerie simultanée est configurée et que le téléphone est éteint, déchargé ou en dehors de la plage.
        
        <div>
        

        > [!NOTE]  
        > Cette fonctionnalité est configurable uniquement par le biais de Lync Server Management Shell

        
        </div>
    
      - **Transfert d’appel** permet aux utilisateurs de transférer des appels vers d’autres téléphones et périphériques clients. Lync Server 2013 offre un large éventail d’options de configuration pour le transfert d’appel. Par exemple, si une organisation ne souhaite pas autoriser le transfert des appels entrants à l’extérieur vers le réseau téléphonique commuté (PSTN), un administrateur peut appliquer une stratégie de voix spéciale pour déployer cette restriction. Activée par défaut.
    
      - **Délégation** permet aux utilisateurs de spécifier d’autres utilisateurs pouvant passer et recevoir des appels à leur place. Dans Lync Server 2013, un délégué peut configurer la sonnerie simultanée qui permet aux appels entrants vers son responsable de sonner dans toutes les cibles de sonnerie simultanées du délégué. Le délégué peut ainsi répondre avec une plus grande souplesse aux appels destinés au responsable. Activée par défaut.
    
      - **Transfert d’appel** permet aux utilisateurs de transférer des appels à d’autres utilisateurs. Activée par défaut.
    
      - **Parcage d’appel** permet aux utilisateurs de parquer des appels en attente, puis de les reprendre depuis un autre téléphone ou client. Désactivée par défaut.
    
      - **Sonnerie simultanée** permet aux appels entrants de sonner sur des téléphones supplémentaires (par exemple, un téléphone mobile) ou d’autres périphériques de système d’extrémité. Lync Server 2013 offre un large éventail d’options de configuration pour la sonnerie simultanée. Activée par défaut.
    
      - **Appel d’équipe** permet aux utilisateurs d’une équipe définie de répondre aux appels destinés à d’autres membres de l’équipe. Activée par défaut.
    
      - **Réacheminement PSTN** permet aux appels des utilisateurs (auxquels cette stratégie est affectée) destinés à d’autres utilisateurs de l’entreprise d’être réacheminés sur le réseau téléphonique commuté (PSTN) si le réseau étendu (WAN) est saturé ou indisponible. Activée par défaut.
    
      - Le **remplacement de stratégie de bande passante** permet aux administrateurs de remplacer les décisions de stratégie du contrôle d’admission des appels pour un utilisateur particulier. Désactivée par défaut.
        
        <div>
        

        > [!NOTE]  
        > La stratégie sera uniquement remplacée pour les appels entrants vers l’utilisateur et non pour les appels sortants qui sont passés par l’utilisateur. Une fois la session établie, la consommation de bande passante est précisément enregistrée. Ce paramètre doit être utilisé avec modération et doit être réservé à la prise de décision appropriée en matière de contrôle d’admission des appels.

        
        </div>
    
      - **Suivi des appels malveillants** permet aux utilisateurs de consigner des appels malveillants (comme une alerte à la bombe) à l’aide de l’interface utilisateur du client, qui signale ensuite ces appels dans les enregistrements des détails des appels (CDR). Désactivée par défaut.

8.  Afin d’associer et de configurer des enregistrements d’utilisation PSTN pour cette stratégie de voix, effectuez l’une des opérations suivantes :
    
      - Pour choisir un ou plusieurs enregistrements dans une liste de tous les enregistrements d’utilisation PSTN disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**. Sélectionnez les enregistrements à associer à cette stratégie de voix, puis cliquez sur **OK**.
    
      - Pour supprimer un enregistrement d’utilisation PSTN de cette stratégie de voix, sélectionnez l’enregistrement et cliquez sur **Supprimer**.
    
      - Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette stratégie de voix, procédez comme suit :
        
        1.  Cliquez sur **Nouveau**.
        
        2.  Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement. Par exemple, vous pouvez créer un enregistrement d’utilisation PSTN appelé **Redmond** pour les employés qui travaillent à plein temps situés à Redmond et un autre appelé **RedmondTemps** pour les employés qui travaillent à temps partiel.
            
            <div>
            

            > [!NOTE]  
            > Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ <STRONG>Nom</STRONG> ne peut plus être modifié.

            
            </div>
        
        3.  Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :
            
              - Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.
            
              - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.
            
              - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        4.  Cliquez sur **OK**.
    
      - Pour modifier un enregistrement d’utilisation PSTN qui est déjà associé à cette stratégie de voix, procédez comme suit :
        
        1.  Sélectionnez l’enregistrement d’utilisation PSTN que vous voulez modifier, puis cliquez sur **Afficher les détails**.
        
        2.  Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :
            
              - Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.
            
              - Pour supprimer un itinéraire de cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.
            
              - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).
            
              - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
        
        3.  Cliquez sur **OK**.

9.  Organisez les enregistrements d’utilisation PSTN pour obtenir des performances optimales. Pour changer la position d’un enregistrement dans la liste, sélectionnez le nom de l’enregistrement, puis cliquez sur la flèche vers le haut ou vers le bas.
    
    <div>
    

    > [!IMPORTANT]  
    > L’ordre dans lequel les enregistrements d’utilisation apparaissent dans la stratégie de voix est essentiel. Lync Server parcourt la liste du haut vers le bas. Nous vous conseillons d’organiser la liste par fréquence d’utilisation ; par exemple : RedmondLocal, RedmondLongDist, RedmondInternational, RedmondBackup.

    
    </div>

10. Afin d’associer et de configurer des enregistrements d’utilisation PSTN pour le transfert d’appel et la sonnerie simultanée dans cette stratégie de voix, effectuez l’une des opérations suivantes :
    
      - Pour utiliser les mêmes enregistrements d’utilisation PSTN pour le transfert d’appels et la sonnerie simultanée que cette stratégie de voix, sélectionnez l’option **Acheminer à l’aide des utilisations PSTN d’appel** dans le menu déroulant.
    
      - Pour activer le transfert d’appels et la sonnerie simultanée pour les utilisateurs internes de Lync uniquement, sélectionnez l’option **Acheminer vers les utilisateurs internes de Lync uniquement** dans le menu déroulant. Les appels ne seront pas transférés vers des numéros PSTN externes.
    
      - Pour spécifier des enregistrements d’utilisation PSTN pour le transfert d’appels et la sonnerie simultanée différents de ceux utilisés pour cette stratégie de voix, sélectionnez l’option **Acheminer à l’aide d’utilisations PSTN personnalisées** dans le menu déroulant. Cette option affiche un contrôle pour sélectionner des enregistrements d’utilisation PSTN existants ou créer des enregistrements d’utilisation PSTN spécifiquement pour le transfert d’appels et la sonnerie simultanée.
        
          - Pour choisir un ou plusieurs enregistrements dans une liste des enregistrements d’utilisation PSTN pour le transfert d’appels et la sonnerie simultanée, cliquez sur **Sélectionner**. Sélectionnez les enregistrements que vous voulez associer à cette stratégie de transfert d’appels et de sonnerie simultanée, puis cliquez sur **OK**.
        
          - Pour supprimer un enregistrement d’utilisation PSTN de cette stratégie de transfert d’appel et de sonnerie simultanée, sélectionnez l’enregistrement et cliquez sur **Supprimer**.
        
          - Pour définir un nouvel enregistrement d’utilisation PSTN et l’associer à cette stratégie de transfert d’appel et de sonnerie simultanée, procédez comme suit :
            
            1.  Cliquez sur **Nouveau**.
            
            2.  Dans le champ **Nom**, entrez un nom descriptif unique pour l’enregistrement.
                
                <div>
                

                > [!NOTE]  
                > Le nom de l’enregistrement d’utilisation PSTN doit être unique dans le déploiement Voix Entreprise. Une fois que l’enregistrement est enregistré, le champ <STRONG>Nom</STRONG> ne peut plus être modifié.

                
                </div>
            
            3.  Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :
                
                  - Pour choisir un ou plusieurs itinéraires dans la liste de tous les itinéraires disponibles dans votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous voulez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.
                
                  - Pour supprimer un itinéraire de l’enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.
                
                  - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            4.  Cliquez sur **OK**.
        
          - Pour modifier un enregistrement d’utilisation PSTN déjà associé à cette stratégie de voix, procédez comme suit :
            
            1.  Sélectionnez l’enregistrement d’utilisation PSTN à modifier, puis cliquez sur **Afficher les détails**.
            
            2.  Utilisez l’une des méthodes suivantes pour associer et configurer les itinéraires de cet enregistrement d’utilisation PSTN :
                
                  - Pour choisir un ou plusieurs itinéraires dans la liste des itinéraires disponibles de votre déploiement Voix Entreprise, cliquez sur **Sélectionner**, sélectionnez les itinéraires que vous souhaitez associer à cet enregistrement d’utilisation PSTN, puis cliquez sur **OK**.
                
                  - Pour supprimer un itinéraire de cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Supprimer**.
                
                  - Pour définir un nouvel itinéraire et l’associer à cet enregistrement d’utilisation PSTN, cliquez sur **Nouveau**. Pour plus d’informations, consultez [la rubrique créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md).
                
                  - Pour modifier un itinéraire qui est déjà associé à cet enregistrement d’utilisation PSTN, sélectionnez l’itinéraire, puis cliquez sur **Afficher les détails**. Pour plus d’informations, consultez [la rubrique modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md).
            
            3.  Cliquez sur **OK**.

11. (Facultatif) Entrez un numéro pour tester la stratégie de voix, puis cliquez sur **OK**. Les résultats du test apparaissent sous **Numéro traduit à tester**.
    
    <div>
    

    > [!NOTE]  
    > Vous pouvez enregistrer une stratégie de voix qui ne réussit pour l’instant pas le test, puis la reconfigurer ultérieurement. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-test-voice-routing.md">test de routage des communications vocales dans Lync Server 2013</A>.

    
    </div>

12. Cliquez sur **OK**.

13. Dans la page **Stratégie de la voix**, cliquez sur **Valider**, puis sur **Valider tout**.
    
    <div>
    

    > [!NOTE]  
    > À chaque fois que vous créez ou modifiez une stratégie de voix, vous devez exécuter la commande <STRONG>Valider tout</STRONG> pour publier la modification de la configuration. Pour plus d’informations, consultez la rubrique <A href="lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md">publier des modifications en attente dans la configuration du routage des communications vocales dans Lync Server 2013</A> dans la documentation des opérations.

    
    </div>

14. (Facultatif) L’échappement de la messagerie vocale détecte qu’un appel a été immédiatement pris en charge par la messagerie vocale du téléphone mobile de l’utilisateur et déconnecte l’appel vers la messagerie vocale du téléphone mobile. Cela permet à l’appel de continuer de sonner sur les autres systèmes d’extrémité de l’utilisateur, donnant ainsi à l’utilisateur la possibilité de répondre à l’appel. Pour plus d’informations sur la configuration d’une stratégie de messagerie vocale, reportez-vous à la rubrique [configuration de l’échappement de la messagerie vocale dans Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013](lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md)  
[Afficher les enregistrements d’utilisation RTC dans Lync Server 2013](lync-server-2013-view-pstn-usage-records.md)  
[Créer un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-create-a-voice-route.md)  
[Modifier un itinéraire des communications vocales dans Lync Server 2013](lync-server-2013-modify-a-voice-route.md)  
[Publier les modifications en attente de la configuration du routage des communications vocales dans Lync Server 2013](lync-server-2013-publish-pending-changes-to-the-voice-routing-configuration.md)  
[Configuration de l’échappement de la messagerie vocale dans Lync Server 2013](lync-server-2013-configuring-voice-mail-escape.md)  


[Tester le routage des communications vocales dans Lync Server 2013](lync-server-2013-test-voice-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

