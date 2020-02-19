---
title: 'Lync Server 2013 : appliquer le verrouillage du téléphone'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enforce phone locking
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520963(v=OCS.15)
ms:contentKeyID: 48183594
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8473809982a58ccc966482cd72223e0b234dd9ec
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137453"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a>Appliquer le verrouillage du téléphone dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Les appareils Lync Phone Edition peuvent être verrouillés à des fins de sécurité. Si vous appliquez un verrou téléphonique, l’appareil exécutant Lync Phone Edition se bloque après un laps de temps que vous configurez. Lorsqu’un téléphone est verrouillé, un utilisateur peut passer des appels mais ne peut pas accéder aux informations de calendrier et de contact, à la messagerie vocale, ni aux journaux d’appels ou utiliser la recherche. Pour déverrouiller le téléphone, l’utilisateur entre un code confidentiel.

Pour appliquer un verrou téléphonique, activez-le et configurez-le à l’aide du panneau de configuration Lync Server ou des applets de commande Lync Server PowerShell. Vous pouvez appliquer un verrouillage téléphonique global ou uniquement au sein du site pour lequel il est configuré.

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>Pour configurer et appliquer le verrou téléphonique

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Cliquez sur **Clients**, puis sur **Configuration du périphérique**.

4.  Sous l’onglet **Configuration du périphérique**, dans la liste des configurations possibles, double-cliquez sur la configuration pour laquelle vous souhaitez modifier les paramètres de verrouillage du téléphone.

5.  Dans la boîte de dialogue **Modifier la configuration du périphérique**, vérifiez que la case à cocher **Appliquer le verrouillage de l’appareil** est activée.

6.  Dans **longueur minimale du code confidentiel**, acceptez la valeur par défaut pour le nombre minimal de chiffres que le code confidentiel de déverrouillage doit contenir ou spécifiez une nouvelle valeur. La plage de longueur du code confidentiel est comprise entre quatre et 15 chiffres, et la valeur par défaut est six.

7.  Dans **délai d’expiration du verrouillage du téléphone**, acceptez la valeur par défaut pour la durée minimale avant le blocage du téléphone ou spécifiez une nouvelle valeur. La plage du délai d’attente est comprise entre 0 et 60 minutes, et la valeur par défaut est 10. Le format de cette valeur est HH:MM:SS.

8.  Cliquez sur **Valider**.

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>Application du verrouillage de téléphone à l’aide des applets de commande Windows PowerShell

Le verrouillage du téléphone peut être appliqué à l’aide de la cmdlet Set-CsUCPhoneConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-enable-phone-locking"></a>Pour activer le verrouillage du téléphone

  - La commande suivante active le verrouillage du téléphone sur le site de Redmond. Pour désactiver le verrouillage du téléphone, attribuez à la propriété EnforcePhoneLock la valeur Faux ($False).
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>Pour activer le verrouillage du téléphone et modifier le délai d’expiration du verrouillage du téléphone

  - Cette commande active le verrouillage du téléphone et définit également le délai d’expiration du verrouillage sur 30 minutes.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>Pour activer le verrouillage du téléphone au sein de l’Organisation

  - Dans cet exemple, le verrouillage du téléphone est activé sur les paramètres de configuration de tous les téléphones UC utilisés dans l’organisation.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de commande [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Gestion de l’authentification Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  


[Gestion des appareils, des téléphones et des applications clientes dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

