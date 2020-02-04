---
title: 'Lync Server 2013 : cmdlets de sécurité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Security cmdlets
ms:assetid: 9a6c654d-287d-434e-8d93-409f0d623f5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398799(v=OCS.15)
ms:contentKeyID: 48184968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df13c5182d97534e32f0f4d383df73985907c8f1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="security-cmdlets-in-lync-server-2013"></a>Cmdlets de sécurité dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-09_

Les applets de vérification intégrés à Microsoft Lync Server 2013 servent essentiellement à gérer l’authentification, ainsi que les droits et les autorisations des utilisateurs. Une vaste gamme d’applets de commande est disponible pour gérer l’authentification, dont des applets de commande pour l’authentification de certificats et de codes confidentiels (PIN). De plus, un certain nombre d’applets de commande vous permettent d’utiliser la nouvelle fonctionnalité de contrôle d’accès basée sur un rôle pour déléguer le contrôle d’administration de Lync Server.

<div>

## <a name="security-cmdlets"></a>Cmdlets de sécurité

Il est possible d’effectuer de nombreuses tâches de gestion relatives aux paramètres de sécurité à partir du panneau de configuration de Lync Server. Une exception majeure est l’applet de commande d’autorisation de l’utilisateur. Toutefois, toutes les tâches de gestion de la sécurité peuvent être effectuées à l’aide d’applets de interface de Lync Server Management Shell ou à partir d’un script. l’utilisation d’un script vous permet d’automatiser certaines tâches. La liste suivante répertorie les applets de commande qui concernent directement la gestion des paramètres de sécurité :

**[Applets de certification et d’authentification dans Lync Server 2013](lync-server-2013-certificate-and-authentication-cmdlets.md)**

  - <span></span>  
    [Get-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398227(v=OCS.15))

  - <span></span>  
    [Importation-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398688(v=OCS.15))

  - <span></span>  
    [Remove-CsCertificate](https://technet.microsoft.com/en-us/library/Gg412895(v=OCS.15))

  - <span></span>  
    [Requête-CsCertificate](https://technet.microsoft.com/en-us/library/Gg425723(v=OCS.15))

  - <span></span>  
    [Set-CsCertificate](https://technet.microsoft.com/en-us/library/Gg398518(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Test-CsCertificateConfiguration](https://technet.microsoft.com/en-us/library/Gg398647(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg398143(v=OCS.15))

  - <span></span>  
    [Revoke-CsClientCertificate](https://technet.microsoft.com/en-us/library/Gg425748(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Lock-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))

  - <span></span>  
    [Set-CsClientPin](https://technet.microsoft.com/en-us/library/Gg398929(v=OCS.15))

  - <span></span>  
    [Unlock-CsClientPin](unhttps://technet.microsoft.com/en-us/library/Gg398650(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsClientPinInfo](https://technet.microsoft.com/en-us/library/Gg425947(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [New-CsKerberosAccount](https://technet.microsoft.com/en-us/library/Gg398485(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398526(v=OCS.15))

  - <span></span>  
    [New-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398074(v=OCS.15))

  - <span></span>  
    [Remove-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg413052(v=OCS.15))

  - <span></span>  
    [Set-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg398232(v=OCS.15))

  - <span></span>  
    [Test-CsKerberosAccountAssignment](https://technet.microsoft.com/en-us/library/Gg425938(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Set-CsKerberosAccountPassword](https://technet.microsoft.com/en-us/library/Gg398659(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398262(v=OCS.15))

  - <span></span>  
    [Grant-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398871(v=OCS.15))

  - <span></span>  
    [New-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398935(v=OCS.15))

  - <span></span>  
    [Remove-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg398431(v=OCS.15))

  - <span></span>  
    [Set-CsPinPolicy](https://technet.microsoft.com/en-us/library/Gg412997(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg399011(v=OCS.15))

  - <span></span>  
    [Nouveau-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398335(v=OCS.15))

  - <span></span>  
    [Remove-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg398553(v=OCS.15))

  - <span></span>  
    [Set-CsProxyConfiguration](https://technet.microsoft.com/en-us/library/Gg425796(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398701(v=OCS.15))

  - <span></span>  
    [New-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg425857(v=OCS.15))

  - <span></span>  
    [Remove-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg398865(v=OCS.15))

  - <span></span>  
    [Set-CsSipDomain](https://technet.microsoft.com/en-us/library/Gg412949(v=OCS.15))

**[Cmdlets droits d’utilisateur et autorisations dans Lync Server 2013](lync-server-2013-user-rights-and-permissions-cmdlets.md)**

  - <span></span>  
    [Get-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399050(v=OCS.15))

  - <span></span>  
    [Nouveau-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg398271(v=OCS.15))

  - <span></span>  
    [Remove-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg413036(v=OCS.15))

  - <span></span>  
    [Set-CsAdminRole](https://technet.microsoft.com/en-us/library/Gg399066(v=OCS.15))

  - <span></span>  
    [Update-CsAdminRole](https://technet.microsoft.com/en-us/library/JJ204851(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get-CsAdminRoleAssignment](https://technet.microsoft.com/en-us/library/Gg398434(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Grant-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg425739(v=OCS.15))

  - <span></span>  
    [Revoke-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398977(v=OCS.15))

  - <span></span>  
    [Test-CsOUPermission](https://technet.microsoft.com/en-us/library/Gg398787(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Grant-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398569(v=OCS.15))

  - <span></span>  
    [Revoke-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg425834(v=OCS.15))

  - <span></span>  
    [Test-CsSetupPermission](https://technet.microsoft.com/en-us/library/Gg398428(v=OCS.15))

**[Cmdlets d’interopérabilité dans Lync Server 2013](lync-server-2013-interoperability-cmdlets.md)**

  - [Get-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ205155(v=OCS.15))

  - [Set-CsOAuthConfiguration](https://technet.microsoft.com/en-us/library/JJ204841(v=OCS.15))

<!-- end list -->

  - [Get-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205238(v=OCS.15))

  - [New-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205206(v=OCS.15))

  - [Remove-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ205408(v=OCS.15))

  - [Set-CsOAuthServer](https://technet.microsoft.com/en-us/library/JJ204896(v=OCS.15))

<!-- end list -->

  - [Get-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ205128(v=OCS.15))

  - [New-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204628(v=OCS.15))

  - [Remove-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204820(v=OCS.15))

  - [Set-CsPartnerApplication](https://technet.microsoft.com/en-us/library/JJ204755(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Blog Lync Server PowerShell](http://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

