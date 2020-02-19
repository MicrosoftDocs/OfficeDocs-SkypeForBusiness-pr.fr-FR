---
title: Identités, étendues et locataires dans Skype entreprise Online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9dd2008984707f1f8e76b7e61074d5303c0d0819
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137905"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>Identités, étendues et locataires dans Skype entreprise Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2015-03-09_

La plupart des applets de commande Windows PowerShell utilisées pour gérer Skype entreprise Online nécessitent un très grand nombre de détails sur l’élément que vous tentez de gérer. Par exemple, lorsque vous exécutez la cmdlet [Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) , vous devez indiquer l’utilisateur que vous tentez de gérer. Cela est logique. Sauf si vous indiquez spécifiquement à l’applet de commande le compte d’utilisateur à gérer, l’applet de commande **Set-CsUserAcp** n’a aucune idée des informations de conférence audio de l’utilisateur à modifier. Pour cette raison, chaque fois que vous exécutez la cmdlet **Set-CsUserAcp** , vous devez inclure le paramètre Identity, suivi de l’identité du compte d’utilisateur à modifier :

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

Si le terme *Identity* fait toujours référence à l’identité d’un compte d’utilisateur, il n’y aurait pas de risque de confusion. Lorsque vous traitez avec des personnes (utilisateurs, contacts, etc.), les identités font référence aux utilisateurs individuels eux-mêmes. Toutefois, les éléments autres que les comptes d’utilisateur ont également des identités. Lorsque vous gérez des composants du service Skype entreprise Online (stratégies, paramètres de configuration, etc.), le terme Identity signifie quelque peu légèrement différent. Par exemple, considérez la commande suivante :

    Get-CsMeetingConfiguration -Identity "global"

Dans ce cas, l’identité « globale » fait référence à l’étendue des paramètres de configuration de réunion. *Scope* est un terme utilisé dans Skype entreprise Online (et dans Lync Server) pour désigner les sphères de gestion. Par défaut, les stratégies et les paramètres ont toujours une portée globale. Lorsque vous configurez pour la première fois votre compte Skype entreprise Online, vous disposez, par défaut, d’une collection de stratégies et de paramètres globaux (paramètres de configuration de réunion globale), d’une stratégie d’accès externe globale, d’un plan de numérotation global, etc.

Ces stratégies et paramètres globaux ont été introduits dans Microsoft Lync Server 2010 pour garantir que tous les utilisateurs et tous les composants devaient toujours être gérés. Cela n’était pas nécessairement vrai dans Microsoft Office Communicator 2007 R2. En fonction de la manière dont vous avez accédé au système, vous risquez de vous trouver dans un État largement non géré (en général, parce que la stratégie de groupe n’a pas pu être appliquée à votre compte d’utilisateur). En revanche, dans Lync Server et dans Skype entreprise Online, rien n’est jamais laissé non géré. En effet, à la place du reste, les stratégies globales et les paramètres seront toujours appliqués.

Qu’est-ce que nous voulons dire par « à la place de quelque chose » ? En ce qui concerne Skype entreprise Online, il est possible de créer des stratégies au niveau de l' *étendue de la balise*ou d’une sphère de gestion. Les stratégies créées au niveau de l’étendue de la balise (également appelée *étendue par utilisateur*) ont priorité sur les stratégies créées au niveau global. En d’autres termes, une stratégie par utilisateur est toujours prioritaire sur une stratégie globale. Par exemple, vous avez peut-être deux stratégies d’accès des utilisateurs externes. La stratégie globale interdit aux utilisateurs de communiquer avec des personnes disposant de comptes sur des fournisseurs de messagerie instantanée (IM) publics, tels que Windows Live. La stratégie par utilisateur, AllowPublicIMCommunication, permet de communiquer avec des fournisseurs de messagerie instantanée publics.

Vous pouvez également avoir deux utilisateurs : Ken Myer et Pilar Ackerman. La stratégie par utilisateur a été affectée à Ken Myer. Pilar Ackerman n’a pas été affecté à une stratégie par utilisateur ; en d’autres conditions, elle est gérée par la stratégie d’accès externe globale. Le tableau suivant indique l’utilisateur (le cas échéant) qui peut communiquer avec des fournisseurs de messagerie instantanée publics :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Paramètres de stratégie</th>
<th>Ken Myer</th>
<th>Pilar Ackerman</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Paramètre de stratégie globale pour les fournisseurs de messagerie instantanée publics</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Paramètre de stratégie par utilisateur pour les fournisseurs de messagerie instantanée publics</p></td>
<td><p>Oui</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Un utilisateur peut communiquer avec des fournisseurs de messagerie instantanée publics</p></td>
<td><p>Oui</p></td>
<td><p>Non</p></td>
</tr>
</tbody>
</table>


Comme vous pouvez le constater, Ken Myer est autorisé à communiquer avec des fournisseurs de messagerie instantanée publics. Cela est dû au fait que les paramètres de la stratégie par utilisateur qui lui sont attribués remplacent les paramètres dans la stratégie globale. Pilar Ackerman ne peut pas communiquer avec des fournisseurs de messagerie instantanée publics. Cela est dû au fait qu’elle est gérée par la stratégie globale et que la stratégie globale interdit ces communications.

Les stratégies par utilisateur doivent être créées pour vous par la prise en charge d’Office 365. Une fois les stratégies créées, vous pouvez les affecter à des utilisateurs à l’aide de la cmdlet **Grant-CS** appropriée (par exemple, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)). Les stratégies par utilisateur sont faciles à identifier car l’identité de la stratégie commence toujours par le **préfixe**de balise. Par exemple :

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> Les dates de <STRONG>préfixe</STRONG> de balise aux premiers jours de développement de Lync Server 2010. Pendant ces jours, les stratégies par utilisateur étaient appelées <EM>stratégies de balise</EM> et étaient identifiées par le <STRONG>préfixe</STRONG>de balise. Ces stratégies sont désormais plus précisément désignées comme des <EM>stratégies par utilisateur</EM>, et l’étendue de la balise est plus précisément désignée <EM>par l’étendue par utilisateur</EM>. Toutefois, pour des raisons techniques, le <STRONG>préfixe</STRONG> de balise n’a jamais été modifié.



</div>

Un autre terme clé utilisé avec Skype entreprise Online et Windows PowerShell est *client*. Lorsque vous configurez un compte Skype entreprise Online, votre nouveau déploiement se voit attribuer un numéro d’ID de client, qui est un identificateur global unique (GUID) de la manière suivante :

    bf19b7db-6960-41e5-a139-2aa373474354

Quelques-unes des applets de commande Skype entreprise Online vous obligent à entrer l’ID de client chaque fois que vous exécutez l’applet de commande. Vous devez entrer l’ID de client même si vous avez ouvert une session sur, et uniquement un seul client. Heureusement, il n’est pas nécessaire de mémoriser l’ID de client. Vous pouvez récupérer votre ID de client à tout moment en exécutant la commande Windows PowerShell suivante :

    Get-CsTenant | Select-Object TenantId

Bien entendu, connaître la différence entre l’étendue globale et l’étendue par utilisateur (ou l’étendue de la balise) n’est qu’une partie de la bataille. Il est également important de déterminer quand (ou même si) vous pouvez utiliser ces étendues. Il en est de même pour les identités et le paramètre locataire. Les rubriques suivantes décrivent comment les différentes applets de commande Skype entreprise Online utilisent des identités, des étendues et le paramètre client :

  - [Applets de commande dans Skype entreprise Online qui utilisent uniquement l’étendue globale](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Applets de commande dans Skype entreprise Online qui utilisent l’étendue globale et l’étendue de la balise](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Applets de commande dans Skype entreprise Online qui utilisent une identité d’utilisateur](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Applets de commande dans Skype entreprise Online qui utilisent une identité d’utilisateur et l’étendue de la balise](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Applets de commande dans Skype entreprise Online qui utilisent le paramètre client](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Applets de commande dans Skype entreprise Online qui utilisent l’identité d’un fournisseur de services de conférence](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Applets de commande dans Skype entreprise Online qui n’utilisent pas d’étendue ni d’identité](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

