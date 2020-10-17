---
title: 'Lync Server 2013 : activation ou désactivation des notifications de type transmission pour les téléphones Windows'
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
ms.openlocfilehash: e4bcf8ccda422468416ae4c0b486e2e224b17f9f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515471"
---
# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a>Activation ou désactivation des notifications de type transmission pour les téléphones Windows dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Les notifications de type transmission, sous la forme de badges, d’icônes ou d’alertes, peuvent être envoyées à un téléphone Windows même lorsque l’application mobile est inactive. Ces notifications signalent à un utilisateur qu’un événement s’est produit, par exemple une invitation par messagerie instantanée nouvelle ou manquée, ou un message vocal. Vous pouvez activer ou désactiver les notifications de type transmission pour les appareils Windows Phone à l’aide du panneau de configuration Lync Server 2013 ou de Lync Server 2013 Management Shell.

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>Pour activer les notifications de type transmission pour Windows Phone à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Configuration des notifications push**.

4.  Dans la page **Configuration des notifications par émission** , cliquez sur le site que vous souhaitez modifier, cliquez sur le menu **Edition** , puis sur Afficher les **Détails**.

5.  Activez la case à cocher **Activer les notifications push Microsoft**.

6.  Cliquez sur **Valider**.

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>Pour désactiver les notifications de type transmission pour Windows Phone à l’aide du panneau de configuration Lync Server

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur **Configuration des notifications push**.

4.  Dans la page **Configuration des notifications par émission** , cliquez sur le site que vous souhaitez modifier, cliquez sur le menu **Edition** , puis sur Afficher les **Détails**.

5.  Désactivez la case à cocher **Activer les notifications push Microsoft**.

6.  Cliquez sur **Valider**.

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a>Activation ou désactivation des notifications de type transmission pour Windows Phone à l’aide des applets de commande Windows PowerShell

Vous pouvez activer ou désactiver les notifications de type transmission pour Windows Phone à l’aide de la cmdlet **Set-CsPushNotificationConfiguration** . Vous pouvez exécuter cette cmdlet à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync Server 2010 Using Remote PowerShell » (en anglais) à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a>Pour activer les notifications de type transmission pour Windows Phone

  - Pour activer les notifications de type transmission pour Windows Phone, définissez la valeur de la propriété EnableMicrosoftPushNotificationService sur true ($True). Par exemple :
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a>Pour désactiver les notifications de type transmission pour Windows Phone

  - Pour désactiver les notifications de type transmission pour Windows Phone, définissez la valeur de la propriété EnableMicrosoftPushNotificationService sur false ($False). Par exemple :
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

Pour plus d’informations, voir la rubrique d’aide relative à l’applet de commande [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Configuration des notifications de type transmission dans Lync Server 2013](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

