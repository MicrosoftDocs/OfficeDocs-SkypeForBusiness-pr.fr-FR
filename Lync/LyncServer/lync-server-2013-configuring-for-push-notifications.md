---
title: 'Lync Server 2013 : Configuration des notifications push'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring for push notifications
ms:assetid: d77f2c06-0fe6-45d5-8f08-808ab871b3e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690047(v=OCS.15)
ms:contentKeyID: 48185574
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 08492aaa6fc8c9fb6569ad6ad642a5cc1157a2ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-for-push-notifications-in-lync-server-2013"></a>Configuration des notifications push dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-12_

Les notifications de transmission sous forme de badges, d’icônes ou d’alertes peuvent être envoyées à un appareil mobile même lorsque l’application mobile n’est pas active. Les notifications de transmission avertissent un utilisateur d’événements tels qu’une invitation à la messagerie instantanée, une invitation à une nouvelle ou une messagerie vocale. Le service de mobilité Lync Server 2013 envoie les notifications au service de notifications de transmission Lync Server via le Cloud, qui envoie ensuite les notifications au service de notifications de transmission d’Apple (APNS) (pour un appareil Apple exécutant le client mobile Lync 2010) ou le Service de notifications d’appel Microsoft (MPNS) (pour un appareil Windows Phone exécutant l’application mobile Lync 2010 ou le client mobile Lync 2013).

<div>


> [!IMPORTANT]  
> Si vous utilisez un téléphone Windows Phone avec Lync 2010 mobile ou Lync 2013 mobile, la notification de transmission est une considération importante.<BR>Si vous utilisez Lync 2010 mobile sur des appareils Apple, vous devez tenir compte des notifications de transmission.<BR>Si vous utilisez Lync 2013 mobile sur des appareils Apple, vous n’avez plus besoin d’une notification de transmission.



</div>

Configurez votre topologie pour prendre en charge les notifications de transmission en procédant comme suit:

  - Si votre environnement possède un serveur Edge Lync Server 2010 ou Lync Server 2013, vous devez ajouter un nouveau fournisseur d’hébergement, Microsoft Lync Online, puis configurer la Fédération des fournisseurs d’hébergement entre votre organisation et Lync Online.

  - Si votre environnement possède un serveur Edge Office Communications Server 2007 R2, vous devez configurer la Fédération SIP directe avec push.lync.com.
    
    <div>
    

    > [!NOTE]  
    > Push.lync.com est un domaine Microsoft Office 365 pour le service de notifications de transmission.

    
    </div>

  - Pour activer les notifications de transmission, vous devez exécuter l’applet **de cmdlet Set-CsPushNotificationConfiguration** . Par défaut, les notifications push sont désactivées.

  - Testez la configuration de la Fédération et les notifications de transmission.

<div>

## <a name="to-configure-for-push-notifications-with-lync-server-2013-or-lync-server-2010edge-server"></a>Pour configurer les notifications de transmission avec Lync Server 2013 ou Lync Server 2010 Edge Server

1.  Connectez-vous à un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du groupe RtcUniversalServerAdmins.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Ajoutez un fournisseur d’hébergement Lync Server online. Dans la ligne de commande, tapez :
    
        New-CsHostingProvider -Identity <unique identifier for Lync Online hosting provider> -Enabled $True -ProxyFqdn <FQDN for the Access Server used by the hosting provider> -VerificationLevel UseSourceVerification
    
    Exemple :
    
        New-CsHostingProvider -Identity "LyncOnline" -Enabled $True -ProxyFqdn "sipfed.online.lync.com" -VerificationLevel UseSourceVerification
    
    <div>
    

    > [!NOTE]  
    > Vous ne pouvez pas avoir plusieurs relations de Fédération avec un seul fournisseur d’hébergement. Autrement dit, si vous avez déjà configuré un fournisseur d’hébergement ayant une relation de Fédération avec sipfed.online.lync.com, n’ajoutez pas d’autre fournisseur d’hébergement, même si l’identité du fournisseur d’hébergement n’est pas LyncOnline.

    
    </div>

4.  Configurez la Fédération des fournisseurs d’hébergement entre votre organisation et le service de notifications de transmission de Lync Online. À partir de la ligne de commande, tapez :
    
        New-CsAllowedDomain -Identity "push.lync.com"

</div>

<div>

## <a name="to-configure-for-push-notifications-with-office-communications-server-2007-r2edge-server"></a>Pour configurer les notifications de transmission avec un serveur Edge Office Communications Server 2007 R2

1.  Ouvrez une session sur le serveur Edge en tant que membre du groupe RtcUniversalServerAdmins.

2.  Cliquez sur **Démarrer**, sur **tous les programmes**, sur **Outils d’administration**, puis sur gestion de l' **ordinateur**.

3.  Dans l’arborescence de la console, développez **services et applications**, cliquez avec le bouton droit sur **Microsoft Office Communications Server 2007 R2**, puis cliquez sur **Propriétés**.

4.  Dans l’onglet **autoriser** , cliquez sur **Ajouter**.

5.  Dans la boîte de dialogue **Ajouter un partenaire fédéré** , procédez comme suit:
    
      - Dans **nom de domaine du partenaire fédéré**, entrez **push.Lync.com**.
    
      - Dans **serveur Edge d’accès du partenaire fédéré**, entrez **sipfed.online.Lync.com**.
    
      - Cliquez sur **OK**.

</div>

<div>

## <a name="to-enable-push-notifications"></a>Pour activer les notifications de transmission

1.  Connectez-vous à un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Activez les notifications de transmission. À partir de la ligne de commande, tapez :
    
        Set-CsPushNotificationConfiguration -EnableApplePushNotificationService $True -EnableMicrosoftPushNotificationService $True

4.  Activez la Fédération. À partir de la ligne de commande, tapez :
    
        Set-CsAccessEdgeConfiguration -AllowFederatedUsers $True

</div>

<div>

## <a name="to-test-federation-and-push-notifications"></a>Pour tester la Fédération et les notifications de transmission

1.  Connectez-vous à un ordinateur sur lequel Lync Server Management Shell et OCSCore sont installés en tant que membre du rôle CsAdministrator.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  Testez la configuration de la Fédération. Dans la ligne de commande, tapez :
    
        Test-CsFederatedPartner -TargetFqdn <FQDN of Access Edge server used for federated SIP traffic> -Domain <FQDN of federated domain> -ProxyFqdn <FQDN of the Access Edge server used by the federated organization>
    
    Exemple :
    
        Test-CsFederatedPartner -TargetFqdn accessproxy.contoso.com -Domain push.lync.com -ProxyFqdn sipfed.online.lync.com

4.  Testez les notifications de transmission. Dans la ligne de commande, tapez :
    
        Test-CsMcxPushNotification -AccessEdgeFqdn <Access Edge service FQDN>
    
    Exemple :
    
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

