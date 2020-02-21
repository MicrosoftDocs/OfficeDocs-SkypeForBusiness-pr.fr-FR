---
title: 'Lync Server 2013 : rapports sur les affectations de comptes Kerberos'
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
ms.openlocfilehash: 2f44f187b751ec9baa78df8890e64332070d8b33
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="report-kerberos-account-assignments-in-lync-server-2013"></a>Rapports sur les affectations de comptes Kerberos dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-01-16_

Pour effectuer cette procédure vous devez avoir ouvert une session en tant qu’utilisateur membre du groupe RTCUniversalServerAdmins.

Vous pouvez utiliser l’applet de commande **Get-CsKerberosAccountAssignment** pour rechercher des informations sur les affectations de compte d’authentification Kerberos et des informations de rapport sur les affectations actuelles dans votre déploiement.

<div>

## <a name="to-query-kerberos-authentication-account-assignments-for-a-site"></a>Pour rechercher des affectations de compte d’authentification Kerberos pour un site

1.  En tant que membre du groupe RTCUniversalServerAdmins, ouvrez une session sur un ordinateur du domaine exécutant Lync Server 2013 ou sur un ordinateur sur lequel les outils d’administration sont installés.

2.  Démarrez Lync Server Management Shell : cliquez sur **Démarrer **, **Tous les programmes **, **Microsoft Lync Server 2013 **, puis sur **Lync Server Management Shell**.

3.  Depuis la ligne de commande, exécutez l’une des commandes suivantes :
    
      - Pour rechercher toutes les affectations de compte d’authentification Kerberos dans votre organisation et renvoyer les informations d’affectation sur chacune d’entre elles, exécutez l’applet de commande sans aucun paramètre :
        
            Get-CsKerberosAccountAssignment
    
      - Pour rechercher toutes les affectations de compte d’authentification Kerberos dans votre déploiement et renvoyer les informations d’affectation de site sur chacune d’entre elles, exécutez l’applet de commande avec le paramètre Identity :
        
            Get-CsKerberosAccountAssignment -Identity "site:SiteName"
        
        Par exemple :
        
            Get-CsKerberosAccountAssignment -Identity "site:Redmond"
    
      - Pour rechercher toutes les affectations de compte d’authentification Kerberos dans un seul site et renvoyer les informations d’affectation sur chacune d’entre elles, exécutez l’applet de commande avec le paramètre Filter :
        
            Get-CsKerberosAccountAssignment -Filter "SiteName"
        
        Par exemple :
        
            Get-CsKerberosAccountAssignment -Filter "*Redmond"
        
        <div>
        

        > [!NOTE]  
        > Si vous spécifiez *SiteName pour le paramètre Filter, le système renvoie les informations sur tous les sites qui contiennent le nom de site spécifié partout dans l’identificateur de site (par exemple, tous les sites qui contiennent la chaîne Redmond dans l’identificateur de site).

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

