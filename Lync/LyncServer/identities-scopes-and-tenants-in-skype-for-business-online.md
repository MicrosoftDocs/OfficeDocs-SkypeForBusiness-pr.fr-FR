---
title: Identités, étendues et clients dans Skype entreprise Online
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Identities, scopes, and tenants
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56558817
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a759c53b717cbaf1ecdb747d5cb01e94b305f52
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838871"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="identities-scopes-and-tenants-in-skype-for-business-online"></a>Identités, étendues et clients dans Skype entreprise Online

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2015-03-09_

La plupart des cmdlets Windows PowerShell utilisées pour gérer Skype entreprise Online nécessitent que vous soyez extrêmement précis de l’élément que vous tentez de gérer. Par exemple, lorsque vous exécutez l’applet [de cmdlet Set-CsUserAcp](https://docs.microsoft.com/powershell/module/skype/Set-CsUserAcp) , vous devez indiquer l’utilisateur que vous voulez gérer. C’est un bon sentiment. À moins que vous ne soyez spécifiquement en informant sur le compte d’utilisateur à gérer, l’applet **de passe Set-CsUserAcp** n’a aucune idée des informations de l’utilisateur à modifier. Pour cette raison, chaque fois que vous exécutez l’applet **de connexion Set-CsUserAcp** , vous devez inclure le paramètre Identity, suivi de l’identité du compte d’utilisateur à modifier:

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

Si le terme *identité* correspond toujours à l’identité d’un compte d’utilisateur, il n’y a pas de raison de confusion. Lorsque vous travaillez avec des personnes (utilisateurs, contacts, etc.), les identités font référence aux utilisateurs individuels eux-mêmes. Toutefois, les éléments autres que les comptes d’utilisateurs sont également dotés d’identités. Lorsque vous travaillez avec des composants du service Skype entreprise Online (politiques, paramètres de configuration, etc.), le terme identité désigne un aspect légèrement différent. Par exemple, utilisez la commande suivante:

    Get-CsMeetingConfiguration -Identity "global"

Dans ce cas, l’identité «global» fait référence à l’étendue des paramètres de configuration de la réunion. *Scope* est un terme utilisé dans Skype entreprise Online (et dans Lync Server) pour désigner les sphères de gestion. Par défaut, les stratégies et les paramètres disposent toujours d’une étendue globale. Lorsque vous configurez votre compte Skype entreprise Online pour la première fois, vous disposez par défaut d’une collection de stratégies globales et de paramètres: les paramètres de configuration de réunion globale, une stratégie d’accès externe globale, un plan de numérotation global, etc.

Ces stratégies et paramètres globaux ont été introduits dans Microsoft Lync Server 2010 pour garantir la gestion de tous les utilisateurs et de tous les composants, d’une certaine façon. Ce n’est pas nécessairement vrai dans Microsoft Office Communicator 2007 R2. En fonction de la manière dont vous avez accédé au système, vous risquez de vous trouver dans un état essentiellement non géré (en général, la stratégie de groupe n’ayant pas pu être appliquée à votre compte d’utilisateur). En revanche, dans Lync Server et dans Skype entreprise Online, rien n’est jamais laissé non plus. En effet, les stratégies globales et les paramètres sont toujours appliqués en tout lieu.

Qu’est-ce que nous voulons dire par «au lieu de tout autre»? Dans le cas de Skype entreprise Online, il est possible de créer des politiques au niveau de l' *étendue*des balises ou de la sphère de gestion. Les stratégies créées à l’étendue des balises (également connues sous le nom d' *étendue par utilisateur*) sont prioritaires sur les stratégies créées au niveau de l’étendue globale. En d’autres termes, une stratégie par utilisateur sera toujours prioritaire sur une stratégie globale. Par exemple, vous pouvez avoir deux stratégies d’accès utilisateur externes. La stratégie globale interdit aux utilisateurs de communiquer avec des personnes disposant de comptes sur des fournisseurs de messagerie instantanée (IM) publics tels que Windows Live. La stratégie par utilisateur, AllowPublicIMCommunication, permet de communiquer avec les fournisseurs de messagerie instantanée publics.

Vous pouvez également avoir deux utilisateurs: Ken Myer et Pilar Arès. Ken Myer a été affecté de la stratégie par utilisateur. Pilar Arès n’a pas été affecté d’une stratégie par utilisateur; c’est-à-dire qu’elle est gérée par la stratégie d’accès externe globale. Le tableau suivant indique quels utilisateurs (le cas échéant) peuvent communiquer avec les fournisseurs de messagerie instantanée publics:


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
<td><p>L’utilisateur peut communiquer avec les fournisseurs de messagerie instantanée publics</p></td>
<td><p>Oui</p></td>
<td><p>Non</p></td>
</tr>
</tbody>
</table>


Comme vous pouvez le constater, Ken Myer est autorisé à communiquer avec les fournisseurs de messagerie instantanée publics. En effet, les paramètres de la stratégie par utilisateur qui lui sont attribués remplacent ceux de la stratégie globale. Pilar Arès ne peut pas communiquer avec les fournisseurs de messagerie instantanée publics. C’est parce qu’elle est gérée par la stratégie globale et que la stratégie globale interdit ces communications.

Des stratégies par utilisateur doivent être créées pour vous par le biais du support technique d’Office 365. Une fois les stratégies créées, vous pouvez les affecter aux utilisateurs à l’aide de l’applet de passe **Grant-CS** appropriée (par exemple, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/powershell/module/skype/Grant-CsExternalAccessPolicy)). Les stratégies par utilisateur sont faciles à identifier, car l’identité de la stratégie commence toujours **** par le préfixe de la balise. Par exemple :

    Identity : tag:AllowPublicIMCommunication

<div>


> [!NOTE]  
> Le <STRONG>préfixe</STRONG> de l’indicateur passe aux jours de développement premiers de Lync Server 2010. Dans ces jours, les politiques par utilisateur étaient appelées <EM>stratégies d’étiquette</EM> et identifiées par le préfixe de balise. <STRONG></STRONG> Ces stratégies sont désormais plus précises que celles définies <EM>par l’utilisateur</EM>, et l’étendue de la balise est désignée de façon plus précise comme <EM>une étendue par utilisateur</EM>. Toutefois, pour des raisons techniques, le <STRONG>préfixe</STRONG> d’indicateur n’a jamais changé.



</div>

Un autre terme clé utilisé lors de l’utilisation de Skype entreprise Online et de Windows PowerShell est le *client*. Lorsque vous configurez un compte Skype entreprise Online, votre nouveau déploiement dispose d’un numéro d’ID de client, qui est un identificateur global unique (GUID), semblable à ce qui suit:

    bf19b7db-6960-41e5-a139-2aa373474354

Quelques-unes des cmdlets de Skype entreprise Online vous demandent d’entrer l’ID de locataire chaque fois que vous exécutez l’applet de connexion. Vous devez entrer l’ID de locataire même si vous vous êtes connecté à un seul client. Heureusement, il n’est pas nécessaire de mémoriser l’ID de locataire. Vous pouvez récupérer votre ID de locataire à tout moment en exécutant la commande Windows PowerShell suivante:

    Get-CsTenant | Select-Object TenantId

Bien entendu, il n’y a pas de différence entre l’étendue globale et l’étendue par utilisateur (ou l’étendue de la balise). Il est également important de savoir quand (ou même si) vous pouvez utiliser ces étendues. Il en va de même pour les identités et le paramètre locataire. Les rubriques suivantes décrivent la façon dont les différentes applets de commande Skype entreprise Online utilisent les identités, les étendues et le paramètre locataire:

  - [Cmdlets dans Skype entreprise Online utilisant uniquement l’étendue globale](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Cmdlets dans Skype entreprise Online utilisant l’étendue globale et l’étendue des indicateurs](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Cmdlets dans Skype entreprise Online utilisant une identité d’utilisateur](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Cmdlets dans Skype entreprise Online utilisant une identité d’utilisateur et une étendue de balises](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Cmdlets dans Skype entreprise Online utilisant le paramètre locataire](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Cmdlets dans Skype entreprise Online utilisant l’identité d’un fournisseur de conférence](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Cmdlets dans Skype entreprise Online qui n’utilisent pas d’étendue ou d’identité](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

</div>

<span> </span>

</div>

</div>

</div>

