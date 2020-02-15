---
title: 'Lync Server 2013 : configuration des notifications de type transmission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f92ae27b919df6a32f06921df97746680a68b030
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028955"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>Configuration des notifications de type transmission dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-12_

Des notifications push, sous forme de badges, icônes ou alertes, peuvent être envoyées à un appareil mobile même si l’application mobile est inactive. Ces notifications signalent à un utilisateur qu’un événement s’est produit, par exemple une invitation par messagerie instantanée nouvelle ou manquée, ou un message vocal. Le service de mobilité Lync Server 2013 envoie les notifications au service de notifications distribuées Lync Server basé sur un nuage, qui envoie ensuite les notifications au service de notifications d’Apple (APNS) Apple (pour un appareil Apple exécutant le client mobile Lync 2010) ou le Microsoft transmission notification service (MPNS) (pour un appareil Windows Phone exécutant Lync 2010 mobile ou le client mobile Lync 2013).

<div>


> [!IMPORTANT]  
> Si vous utilisez Windows Phone avec Lync 2010 mobile ou Lync 2013 mobile client, la notification de transmission est une considération importante.<BR>Si vous utilisez Lync 2010 mobile sur des appareils Apple, la notification de transmission est une considération importante.<BR>Si vous utilisez Lync 2013 mobile sur des appareils Apple, vous n’avez plus besoin d’une notification de transmission.



</div>

Vous pouvez configurer votre topologie de sorte qu’elle prenne en charge les notifications push en procédant comme suit :

  - Si votre environnement comporte un serveur Edge Lync Server 2010 ou Lync Server 2013, vous devez ajouter un nouveau fournisseur d’hébergement, Microsoft Lync Online, puis configurer la Fédération des fournisseurs d’hébergement entre votre organisation et Lync Online.

  - Si votre environnement est doté d’un serveur Edge Office Communications Server 2007 R2, vous devez configurer la Fédération SIP directe avec push.lync.com.
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com est un domaine Microsoft Office 365 pour le service de notifications push.

    
    </div>

  - Pour activer les notifications push, vous devez exécuter l’applet de commande **Set-CsPushNotificationConfiguration**. Par défaut, les notifications push sont désactivées.

  - Testez la configuration de fédération et les notifications push.

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>Pour configurer les notifications de type transmission avec Lync Server 2013 ou Lync Server 2010 serveur Edge

1.  Ouvrez une session sur un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du groupe RtcUniversalServerAdmins.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Ajoutez un fournisseur d’hébergement Lync Server online. Sur la ligne de commande, tapez :
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    Par exemple :
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > Vous ne pouvez pas avoir plus d’une relation de fédération avec un même fournisseur d’hébergement. Autrement dit, si vous avez déjà configuré un fournisseur d’hébergement ayant une relation de fédération avec sipfed.online.lync.com, vous ne devez pas ajouter d’autre fournisseur d’hébergement, même si l’identité du fournisseur d’hébergement est différente de LyncOnline.

    
    </div>

4.  Configurez la fédération de fournisseurs d’hébergement entre votre organisation et le service de notifications push de Lync Online. Sur la ligne de commande, tapez :
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>Pour configurer les notifications de type transmission avec le serveur Edge Office Communications Server 2007 R2

1.  Ouvrez une session sur le serveur Edge en tant que membre du groupe RtcUniversalServerAdmins.

2.  Cliquez sur **Démarrer**, sur **Tous les programmes**, sur **Outils d’administration**, puis sur **Gestion de l’ordinateur**.

3.  Dans l’arborescence de la console, développez **Services et applications**, cliquez avec le bouton droit sur **Microsoft Office Communications Server 2007 R2**, puis cliquez sur **Propriétés**.

4.  Sous l’onglet **Autoriser**, cliquez sur **Ajouter**.

5.  Dans la boîte de dialogue **Ajouter un partenaire fédéré**, procédez comme suit :
    
      - Dans **Nom de domaine du partenaire fédéré**, tapez **push.lync.com**.
    
      - Dans **Serveur Edge d’accès du partenaire fédéré**, tapez **sipfed.online.lync.com**.
    
      - Cliquez sur **OK**.

</div>

<div>

## <a name="to-enable-push-notifications"></a>Pour activer les notifications push

1.  Ouvrez une session sur un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Activez les notifications push. Sur la ligne de commande, tapez :
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  Activez la fédération. Sur la ligne de commande, tapez :
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>Pour tester la fédération et les notifications push

1.  Ouvrez une session sur un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Testez la configuration de la fédération. Sur la ligne de commande, tapez :
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    Par exemple :
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  Testez les notifications push. Sur la ligne de commande, tapez :
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    Par exemple :
    
        Test-CsMcxPushNotification -AccessEdgeFqdn accessproxy.contoso.com

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Test-CsFederatedPartner](https://docs.microsoft.com/powershell/module/skype/Test-CsFederatedPartner)  
[Test-CsMcxPushNotification](https://docs.microsoft.com/powershell/module/skype/Test-CsMcxPushNotification)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

