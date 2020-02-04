---
title: 'Lync Server 2013 : configuration de Lync Server pour utiliser le magasin de contacts unifié'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use the unified contact store
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49733680
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 794d14172c5932436d46fbeb66ea1da4dd7a5e44
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762782"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a>Configuration de Microsoft Lync Server 2013 pour utiliser le magasin de contacts unifié

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-07_

Le magasin de contacts unifié permet aux utilisateurs de mettre à jour une seule liste de contacts et de faire en sorte que ces contacts soient disponibles dans plusieurs applications, notamment Microsoft Lync 2013, Microsoft Outlook 2013 et Microsoft Outlook Web App 2013. Lorsque vous activez le magasin de contacts unifié pour un utilisateur, les contacts qu’il contient ne sont pas stockés dans Microsoft Lync Server 2013, puis extraits via le protocole SIP. Au lieu de cela, ses contacts sont stockés dans Microsoft Exchange Server 2013 et sont récupérés à l’aide des services Web Exchange.

<div>


> [!NOTE]  
> Techniquement, les informations de contact sont stockées dans une paire de dossiers de la boîte aux lettres Exchange 2013 de l’utilisateur. Les contacts eux-mêmes sont stockés dans un dossier nommé contacts Lync qui est visible par les utilisateurs finaux. les métadonnées relatives aux contacts sont stockées dans un sous-dossier qui n’est pas visible pour les utilisateurs finaux.



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a>Activation du magasin de contacts unifié pour un utilisateur

Si vous avez déjà configuré l’authentification de serveur à serveur entre Lync Server 2013 et Exchange 2013, vous pouvez également activer l’utilisation du magasin de contacts unifié. aucune configuration serveur supplémentaire n’est requise. Cependant, il est nécessaire de configurer des comptes utilisateur supplémentaires pour déplacer les contacts d’un utilisateur dans le magasin de contacts unifié. Par défaut, les contacts des utilisateurs sont conservés dans Lync Server et non dans le magasin de contacts unifié.

L’accès au magasin de contacts unifié est géré à l’aide de stratégies de services d’utilisateur Lync Server. Les stratégies de services d’utilisateurs ne possèdent qu’une seule propriété (UcsAllowed) ; celle-ci permet de déterminer l’emplacement dans lequel les contacts de l’utilisateur sont stockés. Si un utilisateur est géré par une stratégie de services d’utilisateur où UcsAllowed a été défini sur true ($True), les contacts de l’utilisateur seront stockés dans le magasin de contacts unifié. Si l’utilisateur est géré par une stratégie de services d’utilisateur où UcsAllowed a été défini sur false ($False), ses contacts seront stockés dans Lync Server.

Lorsque vous installez Lync Server 2013, une stratégie de services d’utilisateur unique (configurée au niveau de l’étendue globale) est également installée. La valeur UcsAllowed dans cette stratégie a la valeur True, ce qui signifie que les contacts de l’utilisateur sont stockés par défaut dans le magasin de contacts unifié (en supposant que celui-ci ait été déployé et configuré). Si vous voulez migrer tous vos contacts utilisateurs vers le magasin de contacts unifié, vous n’avez aucune tâche à effectuer.

Si vous préférez ne pas migrer tous vos contacts vers le magasin de contacts unifié, vous pouvez désactiver celui-ci pour tous les utilisateurs en définissant la propriété UcsAllowed de la stratégie globale sur False :

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

Après avoir désactivé le magasin de contacts unifié dans la stratégie globale, vous pouvez créer une stratégie par utilisateur qui permet d’utiliser le magasin de contacts unifié ; Cela vous permet de faire en sorte que certains utilisateurs gardent leurs contacts dans le magasin de contacts unifié tandis que d’autres utilisateurs continuent à conserver leurs contacts dans Lync Server. Vous pouvez créer une stratégie de services utilisateur par utilisateur à l’aide d’une commande similaire à celle-ci :

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

Après avoir créé la stratégie, vous devez l’affecter à tout utilisateur ayant besoin d’accéder au magasin de contacts unifié. Les stratégies par utilisateur peuvent être affectées aux utilisateurs à l’aide de commandes semblables à ce qui suit :

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

Une fois la stratégie attribuée, le serveur Lync va commencer à migrer les contacts de l’utilisateur vers le magasin de contacts unifié. Une fois la migration terminée, l’utilisateur aura ses contacts stockés dans Exchange plutôt que dans Lync Server. Si l’utilisateur se connecte à Lync 2013 au terme de la migration, une boîte de dialogue s’affiche pour vous demander de vous déconnecter de Lync, puis reconnectez-vous pour finaliser le processus. Les utilisateurs auxquels cette stratégie par utilisateur n’a pas été affectée ne verront pas leurs contacts migrer vers le magasin de contacts unifié. En effet, ces utilisateurs sont gérés par la stratégie globale et l’utilisation du magasin de contacts unifié a été désactivée dans la stratégie globale.

Vous pouvez vérifier que les contacts d’un utilisateur ont bien été migrés vers le magasin de contacts unifié en exécutant l’applet de [contrôle CsUnifiedContactStore de test](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) à partir de Lync Server Management Shell :

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

Si Test-CsUnifiedContactStore réussit, cela signifie que les contacts de l’utilisateur sip:kenmyer@litwareinc.com ont été migrés vers le magasin de contacts unifié.

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a>Restauration du magasin de contacts unifié

Si vous avez besoin de supprimer les contacts d’un utilisateur du magasin de contacts unifié (par exemple, si l’utilisateur doit être rapatrié sur Microsoft Lync Server 2010 et ne peut donc plus utiliser le magasin de contacts unifié), vous devez effectuer deux opérations. Tout d’abord, vous devez affecter à l’utilisateur une nouvelle stratégie de services d’utilisateur, qui empêche le stockage de contacts dans le magasin de contacts unifié. (Il s’agit d’une stratégie dans laquelle la propriété UcsAllowed a été définie sur $False.) Si vous n’avez pas de telle stratégie, vous pouvez en créer une à l’aide d’une commande similaire à celle-ci :

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

Vous pouvez ensuite affecter cette nouvelle stratégie par utilisateur (NoUnifiedContactStore) à l’aide d’une commande semblable à celle-ci :

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

La commande précédente affecte la nouvelle stratégie à l’utilisateur Ken Myer et empêche la migration des contacts de Ken vers le magasin de contacts unifié.

<div>


> [!NOTE]  
> Dans certains cas, vous pouvez obtenir le même effet net en annulant simplement l’attribution de la stratégie de services des utilisateurs actuels de l’utilisateur. Par exemple, supposons que Ken Myer possède une stratégie de services d’utilisateurs par utilisateur qui active le magasin de contacts unifié, alors que votre stratégie globale interdit l’utilisation du magasin de contacts unifié. Dans ce cas, vous pouvez annuler l’affectation de la stratégie de services par utilisateur de Ken. Il est alors automatiquement géré par la stratégie globale et n’a donc plus accès au magasin de contacts unifié.<BR>Pour annuler l’affectation d’une stratégie par utilisateur déjà attribuée, utilisez la même commande que celle présentée précédemment, mais cette fois définissez le paramètre PolicyName sur une valeur NULL :<BR>Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null



</div>

Lorsque vous travaillez avec le magasin de contacts unifié, il est important de garder à l’esprit que la commande « empêche la migration des contacts de Ken vers le magasin de contacts unifié ». Le simple fait d’affecter une nouvelle stratégie de services d’utilisateurs à Ken ne déplace pas ses contacts hors du magasin de contacts unifié. Lorsqu’un utilisateur ouvre une session sur Lync Server 2013, le système vérifie la stratégie des services des utilisateurs de l’utilisateur pour déterminer si ses contacts doivent être conservés dans le magasin de contacts unifié. Si la réponse est oui (c’est-à-dire si la propriété UcsAllowed a la valeur $True), les contacts sont migrés vers le magasin de contacts unifié (en supposant que ces contacts ne se trouvent pas déjà dans le magasin de contacts unifié). Si la réponse est non, Lync Server ignore simplement les contacts de l’utilisateur et passe à sa tâche suivante. Cela signifie que Lync Server ne déplace pas automatiquement les contacts d’un utilisateur du magasin de contacts unifié, quelle que soit la valeur de la propriété UcsAllowed.

Par ailleurs, une fois que vous avez attribué à l’utilisateur une nouvelle stratégie de services d’utilisateur, vous devez exécuter l’applet de commande [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) afin de transférer les contacts de l’utilisateur à partir du serveur Exchange 2013 et de revenir à Lync Server 2013. Par exemple, après avoir affecté une nouvelle stratégie de services d’utilisateurs à Ken Myer, vous pouvez déplacer ses contacts hors du magasin de contacts unifié à l’aide de la commande suivante :

    Invoke-CsUcsRollback -Identity "Ken Myer"

Si vous modifiez la stratégie de services d’utilisateurs sans exécuter l’applet de commande Invoke-CsUcsRollback, les contacts de Ken ne sont pas supprimés du magasin de contacts unifié. Que se passe-t-il si vous exécutez Invoke-CsUcsRollback sans modifier la stratégie de services d’utilisateurs de Ken Myer ? Dans ce cas, les contacts de Ken sont temporairement supprimés du magasin de contacts unifié. Il est important de noter que cette suppression est temporaire. Après la suppression des contacts de Ken du magasin de contacts unifié, Lync Server 2013 attend 7 jours, puis vérifie la stratégie de services utilisateur qui a été attribuée à Ken. Si une stratégie qui autorise l’utilisation du magasin de contacts unifié est toujours affectée à Ken, ses contacts sont automatiquement replacés dans le magasin de contacts. Pour supprimer définitivement les contacts du magasin de contacts unifié, vous devez non seulement modifier la stratégie de services d’utilisateurs, mais aussi exécuter l’applet de commande Invoke-CsUcsRollback.

Compte tenu du grand nombre de variables pouvant affecter la migration, il est difficile d’estimer le délai nécessaire pour migrer totalement les comptes vers le magasin de contacts unifié. En règle générale, cependant, la migration n’a pas un effet immédiat : même lors de la migration d’un petit nombre de contacts, cela peut prendre 10 minutes au moins avant la fin du transfert.

</div>

</div>

<span> </span>

</div>

</div>

</div>

