---
title: Test des adresses postales par rapport au guide principal des adresses
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Testing civic addresses against the master street address guide
ms:assetid: dc680de9-2a0f-4fd3-a99e-9bab0bc30ae5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn690132(v=OCS.15)
ms:contentKeyID: 63969657
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfa4dd28ec05546366e029b6fb9fdf1c4b3ae310
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846552"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="testing-civic-addresses-against-the-master-street-address-guide-in-lync-server-2013"></a>Test des adresses postales par rapport au Guide d’adresses principal dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-06-05_


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Échéancier de vérification</p></td>
<td><p>Jour</p></td>
</tr>
<tr class="even">
<td><p>Outil de test</p></td>
<td><p>Windows PowerShell</p></td>
</tr>
<tr class="odd">
<td><p>Autorisations requises</p></td>
<td><p>Lorsque l’application est exécutée localement à l’aide de Lync Server Management Shell, les utilisateurs doivent être membres du groupe de sécurité RTCUniversalServerAdmins.</p>
<p>Lors de l’exécution à l’aide d’une instance distante de Windows PowerShell, un rôle RBAC doit être attribué aux utilisateurs qui ont l’autorisation d’exécuter l’applet de commande test-CsRegistration. Pour afficher la liste de tous les rôles RBAC qui peuvent utiliser cette applet de commande, exécutez la commande suivante à partir de l’invite Windows PowerShell:</p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsLisCivicAddress &quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a>Description

L’applet de contrôle test-CsLisCivicAddress est utilisée pour vérifier les emplacements qui ont été ajoutés à votre base de données de service d’information d’emplacement (LIS). L’applet de contrôle fonctionne en comparant les emplacements figurant dans le Guide de l’adresse principale (MSAG), qui appartient à votre fournisseur de routage réseau E9-1-1. Si vous n’avez pas de fournisseur de routage réseau ou si le fournisseur ne peut pas être atteint, vos tests échoueront.

Si vous ajoutez le paramètre de commutateur UpdateValidationStatus à votre commande, la propriété de base de données MSAGValid correspondante sera définie sur true pour chaque adresse passant le test.

</div>

<div>

## <a name="running-the-test"></a>Exécution du test

L’applet de contrôle test-CsLisCivicAddress peut être utilisée pour tester des adresses individuelles ou pour tester plusieurs adresses. Par exemple, la commande suivante teste une adresse unique située dans Redmond, WA:

    Test-CsLisCivicAddress -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName Main -StreetSuffix St -PostDirectional "" -City Redmond -State WA -PostalCode 98052 -Country US -UpdateValidationStatus

Par comparaison, cette commande teste toutes les adresses figurant actuellement dans votre base de données LIS:

    Get-CsLisCivicAddress | Test-CsLisCivicAddress -UpdateValidationStatus

Pour plus d’informations, consultez la documentation d’aide de l’applet de [contrôle test-CsRegistration](https://technet.microsoft.com/en-us/library/Gg412737(v=OCS.15)) .

</div>

<div>

## <a name="determining-success-or-failure"></a>Détermination du succès ou de l’échec

Test-CsLisCivicAddress rapportera la réussite ou l’échec pour les adresses fournies. Un test d’adresse échoue si l’adresse est introuvable ou si le fournisseur de services ne peut pas être contacté.

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a>Raisons pour lesquelles le test peut avoir échoué

Voici quelques raisons courantes pour lesquelles les tests-CsLisCivicAddress peuvent échouer:

  - Le fournisseur de service LIS n’est peut-être pas disponible. Vous pouvez récupérer l’URL de votre fournisseur de services LIS en exécutant l’applet de recherche Get-CsLisConfiguration:
    
        Get-CsLisConfiguration 
    
    Vous pouvez alors exécuter une commande ping sur cette URL pour vérifier que le fournisseur de services est disponible.

</div>

</div>

<span> </span>

</div>

</div>

</div>

