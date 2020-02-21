---
title: Test des adresses civiques par rapport au Guide des adresses principales des rues
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe41a6bd898c6f23bc746f5922c98113339a5ee7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42194187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a>Test des adresses postales par rapport au Guide d’adresses principales des rues dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Planification de la vérification</p></td>
<td><p>Tous les jours</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsqu’ils sont exécutés localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lorsqu’ils sont exécutés à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter la cmdlet Test-CsRegistration. Pour afficher la liste de tous les rôles RBAC pouvant utiliser cette cmdlet, exécutez la commande suivante à partir de l’invite Windows PowerShell :</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

La cmdlet Test-CsLisCivicAddress est utilisée pour vérifier les emplacements qui ont été ajoutés à votre base de données de service d’informations d’emplacement. L’applet de commande fonctionne en comparant des emplacements par rapport aux emplacements figurant dans le guide des adresses principales (MSAG) qui appartient à votre fournisseur de routage réseau E9-1-1. Si vous n’avez pas de fournisseur de routage réseau ou si le fournisseur ne peut pas être atteint, vos tests échoueront.

Si vous ajoutez le paramètre de commutateur facultatif UpdateValidationStatus à votre commande, la propriété de base de données MSAGValid correspondante est définie sur true pour chaque adresse qui réussit le test.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

La cmdlet Test-CsLisCivicAddress peut être utilisée pour tester des adresses individuelles ou pour tester plusieurs adresses. Par exemple, cette commande teste une seule adresse située à Redmond, WA :

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

Par comparaison, cette commande teste toutes les adresses actuellement présentes dans votre base de données LIS :

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

Pour plus d’informations, reportez-vous à la documentation de l’aide relative à l’applet de commande [test-CsRegistration](https://technet.microsoft.com/library/Gg412737(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination de la réussite ou de l’échec

Test-CsLisCivicAddress signalera la réussite ou l’échec pour les adresses fournies. Un test d’adresse échoue si l’adresse est introuvable ou si le fournisseur de services ne peut pas être contacté.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test a pu échouer

Voici quelques-unes des causes courantes de l’échec de test-CsLisCivicAddress :

  - Le fournisseur de services LIS n’est peut-être pas disponible. Vous pouvez récupérer l’URL de votre fournisseur de services LIS en exécutant la cmdlet Get-CsLisConfiguration :
    
        Get-CsLisConfiguration 
    
    Vous pouvez ensuite exécuter la commande ping sur cette URL pour vérifier que le fournisseur de services est disponible.

</div>

</div>

<span> </span>

</div>

</div>

</div>

