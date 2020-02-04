---
title: 'Lync Server 2013 : renforcer le verrouillage du téléphone'
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
ms.openlocfilehash: 9c781c09db1834d85a1df4532d1484e43d74ca48
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735474"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enforce-phone-locking-in-lync-server-2013"></a>Renforcer le verrouillage du téléphone dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Les appareils Lync Phone Edition peuvent être verrouillés pour des raisons de sécurité. Si vous appliquez le verrouillage du téléphone, l’appareil exécutant Lync Phone Edition se verrouille après un certain temps que vous configurez. Lorsque le téléphone est verrouillé, un utilisateur peut passer des appels mais ne peut pas accéder aux informations de calendrier et de contact, à la messagerie vocale et aux journaux d’appels ou utiliser la recherche. Pour déverrouiller le téléphone, l’utilisateur entre un code confidentiel.

Pour appliquer le verrouillage du téléphone, activez et configurez-le à l’aide du panneau de configuration de Lync Server ou des applets de commande PowerShell Lync Server. Vous pouvez mettre en place le verrouillage du téléphone globalement ou uniquement dans le site pour lequel il est configuré.

<div>

## <a name="to-configure-and-enforce-the-phone-lock"></a>Pour configurer et appliquer le verrouillage du téléphone

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Cliquez sur **clients**, puis sur **configuration**de l’appareil.

4.  Dans l’onglet Configuration de l' **appareil** , dans la liste des configurations d’appareils, double-cliquez sur la configuration pour laquelle vous souhaitez modifier les paramètres de verrouillage du téléphone.

5.  Dans la boîte de dialogue **modifier la configuration** de l’appareil, vérifiez que la case à cocher appliquer le **verrouillage du périphérique** est activée.

6.  Dans **longueur du code confidentiel minimum**, acceptez la valeur par défaut du nombre minimal de chiffres que le code confidentiel doit contenir ou spécifiez une nouvelle valeur. La plage de la longueur du code confidentiel doit être comprise entre 4 et 15 chiffres, et la valeur par défaut est six.

7.  Dans **délai de verrouillage du téléphone**, acceptez la valeur par défaut pour la durée minimale avant que le téléphone ne se verrouille ou en spécifiant une nouvelle valeur. La plage du délai d’expiration est comprise entre 0 et 60 minutes, et la valeur par défaut est 10. Le format de cette valeur est HH:MM:SS.

8.  Cliquez sur **Valider**.

</div>

<div>

## <a name="enforcing-phone-locking-by-using-windows-powershell-cmdlets"></a>Application du verrouillage du téléphone à l’aide des cmdlets Windows PowerShell

Le verrouillage du téléphone peut être appliqué à l’aide de l’applet de passe Set-CsUCPhoneConfiguration. Cette applet de commande peut être exécutée à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell « démarrage rapide : gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell ».

<div>

## <a name="to-enable-phone-locking"></a>Pour activer le verrouillage du téléphone

  - La commande suivante permet de verrouiller le téléphone pour le site de Redmond. Pour désactiver le verrouillage du téléphone, définissez la propriété EnforcePhoneLock sur false ($False).
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-enable-phone-locking-and-modify-the-phone-lock-timeout"></a>Pour activer le verrouillage du téléphone et modifier le délai de verrouillage du téléphone

  - Cette commande active le verrouillage du téléphone et définit également le délai de verrouillage du téléphone sur 30 minutes.
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

</div>

<div>

## <a name="to-enable-phone-locking-throughout-the-organization"></a>Pour activer le verrouillage du téléphone dans l’ensemble de l’Organisation

  - Dans cet exemple, le verrouillage du téléphone est activé sur l’ensemble des paramètres de configuration de téléphone de UC utilisés au sein de l’organisation.
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

</div>

Pour plus d’informations, consultez la rubrique d’aide relative à l’applet de passe [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsUCPhoneConfiguration) .

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Gestion de l’authentification Lync Server 2013](lync-server-2013-managing-lync-server-authentication.md)  


[Gestion des appareils, des téléphones et des applications client dans Lync Server 2013](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

