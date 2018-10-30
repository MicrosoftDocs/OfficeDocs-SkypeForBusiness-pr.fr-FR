---
title: Identités, étendues et clients
TOCTitle: Identités, étendues et clients
ms:assetid: 7cfa194a-2d01-4370-9b48-ee13ff597fa5
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn362819(v=OCS.15)
ms:contentKeyID: 56269617
ms.date: 06/01/2017
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Identités, étendues et clients

 

_**Dernière rubrique modifiée :** 2015-06-22_

De nombreuses applets de commande Windows PowerShell utilisées pour gérer Skype Entreprise Online demandent une grande précision de votre part à propos des éléments que vous voulez gérer. Par exemple, lorsque vous exécutez l’applet de commande [Set-CsUserAcp](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUserAcp), vous devez indiquer quel utilisateur vous voulez gérer. C’est logique. Tant que vous ne lui indiquez pas exactement le compte d’utilisateur à gérer, l’applet de commande **Set-CsUserAcp** ne peut pas savoir quelles informations de conférence audio d’utilisateur doivent être modifiées. C’est pour cela que vous devez indiquer le paramètre Identity, suivi de l’identité du compte d’utilisateur à modifier à chaque exécution de l’applet de commande **Set-CsUserAcp** :

    Set-CsUserAcp -Identity "Ken Myer" -TollNumber "14255551298" -ParticipantPassCode 13761 -Domain "fabrikam.com" -Name "Fabrikam ACP"

Si le terme *Identité* fait toujours référence à l’identité d’un compte d’utilisateur, il existe peu de risque de confusion. Lorsqu’il s’agit de personnes (utilisateurs, contacts, etc.), les identités font référence aux utilisateurs individuels eux-mêmes. Cependant, les éléments différents des comptes d’utilisateur possèdent également des identités. Lorsqu’il s’agit de composants du service Skype Entreprise Online (stratégies, paramètres de configuration, etc.), le terme identité désigne un concept un peu différent. Prenons cette commande, par exemple :

    Get-CsMeetingConfiguration -Identity "global"

Dans ce cas, l’identité « global » fait référence à l’étendue des paramètres de configuration de la réunion. L’*étendue* est un terme utilisé dans Skype Entreprise Online (et dans Lync Server) pour désigner des sphères de gestion. Par défaut, les stratégies et les paramètres ont toujours une étendue globale. Lors de la première configuration de votre compte Skype Entreprise Online, vous disposez par défaut d’une collection de stratégies et de paramètres globaux (des paramètres globaux de configuration de réunion, une stratégie d’accès externe globale, un plan de numérotation global, etc.).

Ces stratégies et paramètres globaux ont été introduits dans Microsoft Lync Server 2010 pour garantir que tous les utilisateurs et tous les composants seraient toujours gérés d’une manière ou d’une autre. Ce n’était pas nécessairement le cas dans Microsoft Office Communicator 2007 R2. Selon la manière dont vous accédiez au système, vous pouviez éventuellement vous retrouver dans un état non géré (en général parce que la stratégie de groupe ne pouvait pas être appliquée à votre compte d’utilisateur). En revanche, dans Lync Server et Skype Entreprise Online, rien n’est jamais non géré. Cela est dû au fait que les stratégies et paramètres globaux seront toujours appliqués de préférence.

Que signifie « de préférence » ? En fait, dans le cas de Skype Entreprise Online, il est possible de créer des stratégies d’*étendue de balise*, ou de sphère de gestion. Les stratégies créées au niveau de l’étendue de balise (ou *étendue définie par l’utilisateur*) ont priorité sur celles créées au niveau de l’étendue globale. Autrement dit, une stratégie définie par l’utilisateur sera toujours supérieure à une stratégie globale. Par exemple, vous pouvez avoir deux stratégies d’accès des utilisateurs externes. La stratégie globale empêche les utilisateurs de communiquer avec des personnes possédant un compte auprès de fournisseurs de messagerie instantanée publics, tels que Windows Live. La stratégie définie par l’utilisateur, AllowPublicIMCommunication, autorise la communication avec des fournisseurs de messagerie instantanée publics.

Vous pouvez également avoir deux utilisateurs : Ken Myer et Pilar Ackerman. La stratégie définie par l’utilisateur a été attribuée à Ken Myer. Aucune stratégie définie par l’utilisateur n’a été attribuée à Pilar Ackerman ; en d’autres termes, elle est gérée par la stratégie d’accès externe globale. Le tableau suivant indique quel utilisateur (le cas échéant) peut communiquer avec des fournisseurs de messagerie instantanée publics :


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
<td><p>Paramètre de stratégie global pour les fournisseurs de messagerie instantanée publics</p></td>
<td><p>Non</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Paramètre de stratégie utilisateur pour les fournisseurs de messagerie instantanée publics</p></td>
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


Comme vous pouvez le voir, Ken Myer est autorisé à communiquer avec des fournisseurs de messagerie instantanée publics. Cela est dû au fait que les paramètres de la stratégie utilisateur qui lui est attribuée remplacent ceux de la stratégie globale. Pilar Ackerman, en revanche, ne peut pas communiquer avec des fournisseurs de messagerie instantanée publics, car elle est gérée par la stratégie globale et celle-ci empêche ce type de communication.

Les stratégies par utilisateur doivent être créées pour vous par le support technique Office 365. Une fois les stratégies créées, vous pouvez les attribuer aux utilisateurs en utilisant l’applet de commande **Grant-Cs** appropriée (par exemple, [Grant-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsExternalAccessPolicy)). Les stratégies utilisateur sont faciles à identifier, car l’identité de stratégie commence toujours par le préfixe **tag**. Par exemple :

    Identity : tag:AllowPublicIMCommunication

> [!NOTE]  
> Le préfixe <strong>tag</strong> date des tout premiers jours du développement de Lync Server 2010. À ce moment-là, les stratégies utilisateur étaient appelées <em>stratégies de balise</em> et étaient identifiées par le préfixe <strong>tag</strong>. Ces stratégies sont désormais appelées de manière plus exacte <em>stratégies utilisateur</em>, de même que l’étendue de balise est appelée <em>étendue utilisateur</em>. Toutefois, pour des raisons techniques, le préfixe <strong>tag</strong> n’a jamais changé.

Un autre terme clé employé lors de l’utilisation de Skype Entreprise Online et Windows PowerShell est *client*. Lors de la configuration d’un compte Skype Entreprise Online, votre nouveau déploiement reçoit un numéro d’identifiant client, qui constitue un GUID (globally unique identifier) semblable au suivant :

    bf19b7db-6960-41e5-a139-2aa373474354

Certaines applets de commande Skype Entreprise Online vous demandent d’entrer un ID de client lors de leur exécution. Vous devez entrer l’ID de client même si vous êtes connecté et que vous n’avez qu’un seul client. Vous ne devez heureusement pas mémoriser l’ID de client. Vous pouvez l’obtenir à tout moment en exécutant la commande Windows PowerShell suivante :

    Get-CsTenant | Select-Object TenantId

Connaître la différence entre l’étendue globale et l’étendue utilisateur (ou étendue de balise) est une chose. C’en est une autre de savoir quand (ou si) vous pouvez utiliser ces étendues. Il en va de même pour les identités et le paramètre Tenant. Les rubriques suivantes décrivent comment les différentes applets de commande Skype Entreprise Online utilisent les identités, les étendues et le paramètre Tenant :

  - [Applets de commande utilisant la portée globale uniquement](cmdlets-in-skype-for-business-online-that-use-only-the-global-scope.md)

  - [Applets de commande utilisant l’étendue globale et l’étendue de balise](cmdlets-in-skype-for-business-online-that-use-the-global-scope-and-the-tag-scope.md)

  - [Applets de commande utilisant l’identité d’un utilisateur](cmdlets-in-skype-for-business-online-that-use-a-user-identity.md)

  - [Applets de commande qui utilisent une identité utilisateur et l’étendue de balise](cmdlets-in-skype-for-business-online-that-use-a-user-identity-and-the-tag-scope.md)

  - [Applets de commande utilisant le paramètre Tenant](cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter.md)

  - [Applets de commande utilisant une identité de fournisseur de services de conférence](cmdlets-in-skype-for-business-online-that-use-a-conferencing-provider-identity.md)

  - [Applets de commande n’utilisant pas une étendue ou une identité](cmdlets-in-skype-for-business-online-that-do-not-use-a-scope-or-an-identity.md)

