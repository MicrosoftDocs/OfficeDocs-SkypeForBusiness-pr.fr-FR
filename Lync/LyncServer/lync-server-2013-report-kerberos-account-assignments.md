---
title: 'Lync Server 2013 : Consignation des affectations de comptes Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Report Kerberos account assignments
ms:assetid: 523231f6-81b3-454b-996d-663d9bd5cf83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398343(v=OCS.15)
ms:contentKeyID: 48184151
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4c5a6c118596acd406c3741c4dd2ee780fd381b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Consignation des affectations de comptes Kerberos dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-01-16_

Pour effectuer cette procédure, vous devez être connecté en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.

Vous pouvez utiliser l’applet de requête **Get-CsKerberosAccountAssignment** pour rechercher des informations sur les affectations de compte d’authentification Kerberos et des informations de rapport sur les affectations actuelles dans votre déploiement.

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>Pour interroger les affectations de compte d’authentification Kerberos pour un site

1.  En tant que membre du groupe RTCUniversalServerAdmins, connectez-vous à un ordinateur du domaine exécutant Lync Server 2013 ou sur un ordinateur sur lequel les outils d’administration sont installés.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer**, sur **tous les programmes**, sur **Microsoft Lync Server 2013**, puis sur **Lync Server Management Shell**.

3.  À partir de la ligne de commande, exécutez l’une des commandes suivantes :
    
      - Pour interroger toutes les affectations de compte d’authentification Kerberos au sein de votre organisation et retourner des informations d’attribution sur chacun d’eux, exécutez l’applet de requête sans paramètres :
        
            Get-CsKerberosAccountAssignment
    
      - Pour interroger toutes les affectations de compte d’authentification Kerberos dans votre déploiement et retourner les informations d’affectation de site sur chacun d’eux, exécutez l’applet de requête avec le paramètre Identity :
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        Par exemple :
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - Pour interroger toutes les affectations de compte d’authentification Kerberos dans un site unique et retourner les informations d’affectation de chacune d’elles, exécutez l’applet de requête avec le paramètre de filtre :
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        Par exemple :
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > Si vous spécifiez * SiteName pour le paramètre de filtre, les informations relatives à tous les sites contenant le nom de site spécifié n’importe où dans l’identificateur de site (par exemple, tous les sites contenant la chaîne Redmond dans l’identificateur de site).

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

