---
title: 'Lync Server 2013 : activation ou désactivation des notifications de transmission pour les téléphones Windows'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49733767
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1b4c8f1f86fa1456230ad4695de0f5b8c56d406
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735628"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a>Activation ou désactivation des notifications de transmission pour les téléphones Windows dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Les notifications de transmission sous forme de badges, d’icônes ou d’alertes peuvent être envoyées à un Windows Phone même lorsque l’application mobile n’est pas active. Les notifications de transmission avertissent un utilisateur d’événements tels qu’une invitation à la messagerie instantanée, une invitation à une nouvelle ou une messagerie vocale. Vous pouvez activer ou désactiver les notifications de transmission pour les appareils Windows Phone à l’aide de Lync Server 2013 Control Panel ou de Lync Server 2013 Management Shell.

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>Pour activer les notifications de transmission pour Windows Phone à l’aide du panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **clients**, puis sur le bouton de navigation **configuration de notifications de transmission** .

4.  Dans la page **configuration de notifications de transmission** , cliquez sur le site que vous voulez modifier, cliquez sur le menu **modifier** , puis cliquez sur Afficher les **Détails**.

5.  Activez la case à cocher **activer les notifications de transmission Microsoft** .

6.  Cliquez sur **Valider**.

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>Pour désactiver les notifications de transmission pour Windows Phone à l’aide du panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **clients**, puis sur le bouton de navigation **configuration de notifications de transmission** .

4.  Dans la page **configuration de notifications de transmission** , cliquez sur le site que vous voulez modifier, cliquez sur le menu **modifier** , puis cliquez sur Afficher les **Détails**.

5.  Décochez la case **activer les notifications de transmission de Microsoft** .

6.  Cliquez sur **Valider**.

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation des notifications de transmission pour Windows Phone à l’aide d’applets de cmdlet Windows PowerShell

Vous pouvez activer ou désactiver les notifications de transmission pour Windows Phone à l’aide de la cmdlet **Set-CsPushNotificationConfiguration** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a>Pour activer les notifications de transmission pour Windows Phone

  - Pour activer les notifications de transmission pour Windows Phone, définissez la valeur de la propriété EnableMicrosoftPushNotificationService sur true ($True). Par exemple :
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a>Pour désactiver les notifications de transmission pour Windows Phone

  - Pour désactiver les notifications de transmission pour Windows Phone, définissez la valeur de la propriété EnableMicrosoftPushNotificationService sur false ($False). Par exemple :
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration des notifications push dans Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

