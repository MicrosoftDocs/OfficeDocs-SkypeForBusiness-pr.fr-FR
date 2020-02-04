---
title: 'Lync Server 2013 : configuration de la Fédération avec Lync Online'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure federation with Lync Online
ms:assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205126(v=OCS.15)
ms:contentKeyID: 48184946
ms.date: 08/15/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba9179f05918504df15a18b35b9c411f23919330
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-federation-of-lync-server-2013-with-lync-online"></a>Configurer la Fédération de Lync Server 2013 avec Lync Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-08-15_

Suivez les étapes décrites dans cette section pour configurer l’interopérabilité entre votre déploiement local et Skype entreprise online.

<span id="a"></span>

<div>

## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Configurer votre service Edge local pour la Fédération avec Skype entreprise Online

La Fédération permet aux utilisateurs de votre déploiement local de communiquer avec les utilisateurs d’Office 365 au sein de votre organisation. Pour configurer la Fédération, exécutez les applets de commande suivantes :

   ```powershell
    Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -UseDnsSrvRouting -EnablePartnerDiscovery $True
   ```

   ```powershell
    New-CSHostingProvider -Identity LyncOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
   ```

</div>

<span id="b"></span>

<div>

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Configurer votre client Skype entreprise Online pour un espace d’adressage SIP partagé

Une adresse SIP (Session Initiation Protocol) est un identificateur unique pour chaque utilisateur d’un réseau, semblable à un numéro de téléphone ou à une adresse de messagerie. Avant d’essayer de déplacer des utilisateurs de Lync en local vers Skype entreprise Online, vous devez configurer votre client Office 365 pour partager l’espace d’adressage SIP (Session Initiation Protocol) avec votre déploiement local. S’il n’est pas configuré, le message d’erreur ci-dessous peut s’afficher :

Move-CsUser : HostedMigration fault: Error=(510), Description=(Le client de cet utilisateur n’est pas activé pour l’espace d’adressage SIP partagé.)

Pour configurer un espace d’adressage SIP partagé, établissez une session PowerShell distante avec Skype entreprise Online, puis exécutez l’applet de commande suivante :
```powershell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```
Pour établir une session PowerShell distante avec Skype entreprise Online, vous devez d’abord installer le module Skype entreprise Online pour Windows PowerShell, que vous pouvez consulter : [http://go.microsoft.com/fwlink/p/?LinkId=391911](http://go.microsoft.com/fwlink/p/?linkid=391911).

Après avoir installé le module, vous pouvez établir une session distante avec les applets de commande suivantes :

   ```powershell
    Import-Module LyncOnlineConnector
   ```

   ```powershell
    $cred = Get-Credential
   ``` 

   ```powershell
    $CSSession = New-CsOnlineSession -Credential $cred
   ```

   ```powershell
    Import-PSSession $CSSession -AllowClobber
   ```

Pour plus d’informations sur l’établissement d’une session PowerShell distante avec Skype entreprise Online, reportez-vous à la rubrique [connexion à Skype entreprise Online à l’aide de Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

Pour plus d’informations sur l’utilisation du module PowerShell de Skype entreprise Online, reportez-vous à la rubrique [utilisation de Windows PowerShell pour gérer Skype entreprise Online](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Nouveau-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/New-CsHostingProvider)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

