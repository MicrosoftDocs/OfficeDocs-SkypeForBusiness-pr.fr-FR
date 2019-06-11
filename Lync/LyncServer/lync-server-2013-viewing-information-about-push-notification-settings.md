---
title: 'Lync Server 2013: affichage d’informations sur les paramètres de notifications de transmission'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da9279d09ab3b344514a472f3fb0f38e7071aabd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846275"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a>Affichage d’informations sur les paramètres de notifications de transmission dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Les notifications de transmission sous forme de badges, d’icônes ou d’alertes peuvent être envoyées à un appareil mobile même lorsque l’application mobile n’est pas active. Les notifications de transmission avertissent un utilisateur d’événements tels qu’une invitation à la messagerie instantanée, une invitation à une nouvelle ou une messagerie vocale. Vous pouvez afficher les paramètres de notifications de transmission des informations pour les appareils mobiles à l’aide de Lync Server 2013 Control Panel ou de Lync Server 2013 Management Shell.

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a>Pour afficher les informations de notifications de transmission depuis le panneau de configuration de Lync Server

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation gauche, cliquez sur **clients**, puis sur le bouton de navigation configuration de notifications de **transmission** .

4.  Dans la page Configuration de notifications de **transmission** , cliquez sur le site que vous souhaitez afficher, cliquez sur le menu **modifier** , puis cliquez sur **afficher les détails**.

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a>Affichage des informations de notifications de transmission à l’aide des cmdlets Windows PowerShell

Vous pouvez afficher les paramètres de configuration de la notification de transmission à l’aide de Windows PowerShell et de l’applet **de cmdlet Get-CsPushNotificationConfiguration** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-view-push-notification-configuration-information"></a>Pour afficher les informations de configuration des notifications de transmission

  - Pour afficher des informations sur les paramètres de configuration de votre notification d’émission, tapez la commande suivante dans Lync Server Management Shell, puis appuyez sur entrée:
    
        Get-CsPushNotificationConfiguration
    
    Vous obtiendrez des indications semblables à ceci :
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

Pour plus d’informations, consultez la rubrique d’aide de l’applet de passe [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) .

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

