---
title: Test et signalement de la disponibilité fonctionnelle de l’authentification Kerberos
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Test and report functional readiness for Kerberos authentication
ms:assetid: d52c39e5-747d-4f29-88aa-30fd6f26b99c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398925(v=OCS.15)
ms:contentKeyID: 48185519
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30dda07eb0152f43f60627fcee3a75b14745eea2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846617"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-and-report-functional-readiness-for-kerberos-authentication-in-lync-server-2013"></a>Test et signalement de la disponibilité fonctionnelle de l’authentification Kerberos dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-01-16_

Pour effectuer cette procédure, vous devez être connecté en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.

Vous pouvez utiliser l’applet de contrôle Windows PowerShell **test-CsKerberosAccountAssignment** pour tester et signaler la disponibilité fonctionnelle d’une affectation de site pour l’authentification Kerberos. Cette commande interroge le site spécifié dans le paramètre d’identité obligatoire. Le paramètre de rapport facultatif implique que l’applet de commande rédige un rapport HTML\\vers C: logs sur l’ordinateur sur lequel la commande est exécutée. Le paramètre facultatif détaillé signale les informations d’activité à l’écran.

<div>

## <a name="to-test-and-report-functional-readiness-for-kerberos-authentication-for-a-site"></a>Pour tester et signaler la compatibilité fonctionnelle pour l’authentification Kerberos pour un site

1.  En tant que membre du groupe RTCUniversalServerAdmins, connectez-vous à un ordinateur du domaine exécutant Lync Server 2013 ou sur l’ordinateur sur lequel les outils d’administration sont installés.

2.  Démarrez Lync Server Management Shell: cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  À partir de la ligne de commande, exécutez la commande suivante:
    
        Test-CsKerberosAccountAssignment -Identity "site:SiteName" -Report "c:\logs\FileName.htm" -Verbose
    
    Par exemple :
    
        Test-CsKerberosAccountAssignment -Identity "site:Redmond" -Report "c:\logs\KerberosReport.htm" -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

