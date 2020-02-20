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
ms.openlocfilehash: 21e39b9584dfc274e9cf525db85d50df6188fac0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-the-unified-contact-store"></a>Configuration de Microsoft Lync Server 2013 pour utiliser le magasin de contacts unifié

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-07_

Le magasin de contacts unifié permet aux utilisateurs de gérer une seule liste de contacts et de les mettre à disposition de plusieurs applications, notamment Microsoft Lync 2013, Microsoft Outlook 2013 et Microsoft Outlook Web App 2013. Lorsque vous activez le magasin de contacts unifié pour un utilisateur, les contacts de cet utilisateur ne sont pas stockés dans Microsoft Lync Server 2013, puis récupérés à l’aide du protocole SIP. Au lieu de cela, ses contacts sont stockés dans Microsoft Exchange Server 2013 et sont récupérés à l’aide des services Web Exchange.

<div>


> [!NOTE]  
> Techniquement, les informations de contact sont stockées dans une paire de dossiers figurant dans la boîte aux lettres Exchange 2013 de l’utilisateur. Les contacts eux-mêmes sont stockés dans un dossier nommé contacts Lync, qui est visible pour les utilisateurs finaux ; les métadonnées relatives aux contacts sont stockées dans un sous-dossier qui n’est pas visible par les utilisateurs finaux.



</div>

<div>

## <a name="enabling-the-unified-contact-store-for-a-user"></a>Activation du magasin de contacts unifié pour un utilisateur

Si vous avez déjà configuré l’authentification de serveur à serveur entre Lync Server 2013 et Exchange 2013, vous avez également activé l’utilisation du magasin de contacts unifié. aucune configuration de serveur supplémentaire n’est requise. Cependant, il est nécessaire de configurer des comptes utilisateur supplémentaires pour déplacer les contacts d’un utilisateur dans le magasin de contacts unifié. Par défaut, les contacts de l’utilisateur sont conservés dans Lync Server et non dans le magasin de contacts unifié.

L’accès au magasin de contacts unifié est géré à l’aide des stratégies des services d’utilisateurs Lync Server. Les stratégies de services d’utilisateurs ne possèdent qu’une seule propriété (UcsAllowed) ; celle-ci permet de déterminer l’emplacement dans lequel les contacts de l’utilisateur sont stockés. Si un utilisateur est géré par une stratégie de services d’utilisateurs où le paramètre ucsallowed a la valeur true ($True), les contacts de l’utilisateur sont stockés dans le magasin de contacts unifié. Si l’utilisateur est géré par une stratégie de services d’utilisateurs où le paramètre ucsallowed a la valeur false ($False), ses contacts seront stockés dans Lync Server.

Lorsque vous installez Lync Server 2013, une stratégie de services d’utilisateurs unique (configurée au niveau de l’étendue globale) est également installée. La valeur le paramètre ucsallowed de cette stratégie est définie sur true, ce qui signifie que, par défaut, les contacts de l’utilisateur sont stockés dans le magasin de contacts unifié (en supposant que cela a été déployé et configuré). Si vous souhaitez migrer tous vos contacts utilisateur vers le magasin de contacts unifié, il n’est pas nécessaire de faire quoi que ce soit.

Si vous ne souhaitez pas migrer tous vos contacts vers le magasin de contacts unifié, vous pouvez désactiver le magasin de contacts unifié pour tous les utilisateurs en définissant la propriété le paramètre ucsallowed dans la stratégie globale sur false :

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

Une fois que vous avez désactivé le magasin de contacts unifié dans la stratégie globale, vous pouvez créer une stratégie par utilisateur qui permet d’utiliser le magasin de contacts unifié. Cela vous permet de faire en sorte que certains utilisateurs conservent leurs contacts dans le magasin de contacts unifié tandis que les autres utilisateurs continuent de conserver leurs contacts dans Lync Server. Vous pouvez créer une stratégie de services utilisateur par utilisateur à l’aide d’une commande semblable à celle-ci :

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

Après avoir créé la stratégie, vous devez l’affecter à tout utilisateur ayant besoin d’accéder au magasin de contacts unifié. Les stratégies par utilisateur peuvent être affectées aux utilisateurs à l’aide de commandes semblables à ce qui suit :

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

Une fois la stratégie affectée, Lync Server commence à migrer les contacts de l’utilisateur vers le magasin de contacts unifié. Une fois la migration terminée, les contacts de l’utilisateur sont stockés dans Exchange au lieu de Lync Server. Si l’utilisateur se connecte à Lync 2013 à la fin de la migration, un message s’affiche et il est invité à se déconnecter de Lync, puis à se reconnecter afin de finaliser le processus. Les utilisateurs auxquels cette stratégie par utilisateur n’a pas été affectée ne seront pas migrés vers le magasin de contacts unifié. Cela est dû au fait que ces utilisateurs sont gérés par la stratégie globale et que l’utilisation du magasin de contacts unifié a été désactivée dans la stratégie globale.

Vous pouvez vérifier que les contacts d’un utilisateur ont bien été migrés vers le magasin de contacts unifié en exécutant l’applet de commande [test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/Test-CsUnifiedContactStore) à partir de Lync Server Management Shell :

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

Si Test-CsUnifiedContactStore réussit, cela signifie que les contacts de l’utilisateur sip:kenmyer@litwareinc.com ont été migrés vers le magasin de contacts unifié.

</div>

<div>

## <a name="rolling-back-the-unified-contact-store"></a>Restauration du magasin de contacts unifié

Si vous devez supprimer les contacts d’un utilisateur du magasin de contacts unifié (par exemple, si l’utilisateur doit être réhébergé sur Microsoft Lync Server 2010 et ne peut donc plus utiliser le magasin de contacts unifié), vous devez effectuer deux opérations. Tout d’abord, vous devez attribuer à l’utilisateur une nouvelle stratégie de services d’utilisateurs, qui interdit le stockage des contacts dans le magasin de contacts unifié. (Autrement dit, une stratégie pour laquelle la propriété le paramètre ucsallowed a été définie sur $False.) Si vous n’avez pas de stratégie de ce type, vous pouvez en créer une à l’aide d’une commande semblable à celle-ci :

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

Vous pouvez ensuite affecter cette nouvelle stratégie par utilisateur (NoUnifiedContactStore) à l’aide d’une commande semblable à celle-ci :

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

La commande précédente affecte la nouvelle stratégie à l’utilisateur Ken Myer et empêche la migration des contacts de Ken vers le magasin de contacts unifié.

<div>


> [!NOTE]  
> Dans certains cas, vous pouvez obtenir le même résultat en annulant simplement l’affectation de la stratégie de services d’utilisateurs actuelle de l’utilisateur. Par exemple, supposons que Ken Myer possède une stratégie de services d’utilisateurs par utilisateur qui active le magasin de contacts unifié, alors que votre stratégie globale interdit l’utilisation du magasin de contacts unifié. Dans ce cas, vous pouvez annuler l’affectation de la stratégie de services par utilisateur à Ken. Il est alors automatiquement géré par la stratégie globale et n’a donc plus accès au magasin de contacts unifié.<BR>Pour annuler l’affectation d’une stratégie par utilisateur précédemment affectée, utilisez la même commande que celle indiquée précédemment, mais cette fois en affectant au paramètre PolicyName la valeur Null :<BR>Grant-CsUserServicesPolicy –Identity "Ken Myer" –PolicyName $Null



</div>

Lorsque vous travaillez avec le magasin de contacts unifié, il est important de garder à l’esprit que la commande « empêche la migration des contacts de Ken vers le magasin de contacts unifié ». Le simple fait d’affecter une nouvelle stratégie de services d’utilisateurs à Ken ne déplace pas ses contacts hors du magasin de contacts unifié. Lorsqu’un utilisateur se connecte à Lync Server 2013, le système vérifie la stratégie des services d’utilisateurs de l’utilisateur pour déterminer si ses contacts doivent être conservés dans le magasin de contacts unifié. Dans l’affirmative (c’est-à-dire si la propriété UcsAllowed a la valeur $True), les contacts sont migrés vers le magasin de contacts unifié (en supposant que ces contacts ne se trouvent pas déjà dans le magasin de contacts unifié). Si la réponse est non, Lync Server ignore simplement les contacts de l’utilisateur et passe à la tâche suivante. Cela signifie que Lync Server ne déplace pas automatiquement les contacts d’un utilisateur hors du magasin de contacts unifié, quelle que soit la valeur de la propriété le paramètre ucsallowed.

Cela signifie également que, après avoir attribué une nouvelle stratégie de services d’utilisateurs à l’utilisateur, vous devez exécuter l’applet de commande [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/Invoke-CsUcsRollback) afin de déplacer les contacts de l’utilisateur en dehors d’Exchange 2013 et de revenir à Lync Server 2013. Par exemple, après avoir affecté une nouvelle stratégie de services d’utilisateurs à Ken Myer, vous pouvez déplacer ses contacts hors du magasin de contacts unifié à l’aide de la commande suivante :

    Invoke-CsUcsRollback -Identity "Ken Myer"

Si vous modifiez la stratégie de services d’utilisateurs sans exécuter l’applet de commande Invoke-CsUcsRollback, les contacts de Ken ne sont pas supprimés du magasin de contacts unifié. Que se passe-t-il si vous exécutez Invoke-CsUcsRollback sans modifier la stratégie de services d’utilisateurs de Ken Myer ? Dans ce cas, les contacts de Ken sont temporairement supprimés du magasin de contacts unifié. Il est important de noter que cette suppression est temporaire. Une fois que les contacts de Ken ont été supprimés du magasin de contacts unifié, Lync Server 2013 attend 7 jours, puis vérifie que la stratégie de services d’utilisateurs a été affectée à Ken. Si une stratégie qui autorise l’utilisation du magasin de contacts unifié est toujours affectée à Ken, ses contacts sont automatiquement replacés dans le magasin de contacts. Pour supprimer définitivement les contacts du magasin de contacts unifié, vous devez non seulement modifier la stratégie de services d’utilisateurs, mais aussi exécuter l’applet de commande Invoke-CsUcsRollback.

En raison du grand nombre de variables qui peuvent affecter la migration, il est difficile d’estimer le temps nécessaire avant la migration complète des comptes vers le magasin de contacts unifié. En règle générale, toutefois, la migration ne prend pas effet immédiatement : même lors de la migration d’un petit nombre de contacts, elle peut prendre 10 minutes ou plus avant la fin du déplacement.

</div>

</div>

<span> </span>

</div>

</div>

</div>

