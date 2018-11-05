---
title: "Conf. de Microsoft Lync Server 2013 pour l’util. du magasin de contact unifié"
TOCtitle: "Conf. de Microsoft Lync Server 2013 pour l’util. du magasin de contact unifié"
ms:assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688083(v=OCS.15)
ms:contentKeyID: 49891385
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de Microsoft Lync Server 2013 pour l’utilisation du magasin de contact unifié

 

_**Dernière rubrique modifiée :** 2014-02-07_

Le magasin de contacts unifié permet aux utilisateurs de gérer une seule liste de contacts et de rendre ces contacts accessibles dans plusieurs applications, y compris Microsoft Lync 2013, Microsoft Outlook 2013 et Microsoft Outlook Web App 2013. Lorsque vous activez le magasin de contacts unifié pour un utilisateur, les contacts de ce dernier ne sont pas stockés dans Microsoft Lync Server 2013 ni récupérés ensuite à l’aide du protocole SIP. Au lieu de cela, les contacts de l’utilisateur sont stockés dans Microsoft Exchange Server 2013 et récupérés à l’aide des services web Exchange.

> [!NOTE]  
> Techniquement, les informations de contact sont stockées dans deux dossiers figurant dans la boîte aux lettres Exchange 2013 de l’utilisateur. Les contacts eux-mêmes sont stockés dans un dossier nommé « Contacts Lync » visible par les utilisateurs finaux. Les métadonnées sur les contacts sont quant à elles stockées dans un sous-dossier qui n’est pas visible par les utilisateurs finaux.

## Activation du magasin de contacts unifié pour un utilisateur

Si vous avez déjà configuré l’authentification de serveur à serveur entre Lync Server 2013 et Exchange 2013, vous avez alors autorisé l’utilisation du magasin de contacts unifié ; aucune configuration du serveur supplémentaire n’est requise. Cependant, il est nécessaire de configurer des comptes utilisateur supplémentaires pour déplacer les contacts d’un utilisateur dans le magasin de contacts unifié. Par défaut, les contacts de l’utilisateur sont conservés dans Lync Server et non dans le magasin de contacts unifié.

L’accès au magasin de contacts unifié est géré au moyen de stratégies de services d’utilisateurs Lync Server. Les stratégies de services d’utilisateurs ne possèdent qu’une seule propriété (UcsAllowed) ; celle-ci permet de déterminer l’emplacement dans lequel les contacts de l’utilisateur sont stockés. Si un utilisateur est géré par une stratégie de services d’utilisateurs où UcsAllowed a la valeur True ($True), les contacts de l’utilisateur sont stockés dans le magasin de contacts unifié. Si l’utilisateur est géré par une stratégie de services d’utilisateurs où UcsAllowed a la valeur False ($False), ses contacts sont stockés dans Lync Server.

Lorsque vous installez Lync Server 2013, une stratégie de services d’utilisateurs unique (configurée au niveau de l’étendue globale) est également installée. La valeur UcsAllowed dans cette stratégie a la valeur True, ce qui signifie que les contacts de l’utilisateur sont stockés par défaut dans le magasin de contacts unifié (à supposer que celui-ci ait été déployé et configuré). Si vous voulez migrer tous vos contacts utilisateurs vers le magasin de contacts unifié, vous n'avez rien à faire du tout.

Si vous préférez ne pas migrer tous vos contacts vers le magasin de contacts unifié, vous pouvez désactiver celui-ci pour tous les utilisateurs en définissant la propriété UcsAllowed de la stratégie globale sur False :

    Set-CsUserServicesPolicy -Identity global -UcsAllowed $False

Une fois que vous avez désactivé le magasin de contacts unifié dans la stratégie globale, vous pouvez alors créer une stratégie par utilisateur autorisant l’utilisation du magasin de contacts unifié. De cette façon, certains utilisateurs peuvent conserver leurs contacts dans le magasin de contacts unifié, alors que d’autres peuvent les conserver dans Lync Server. Vous pouvez créer une stratégie de services d’utilisateurs par utilisateur à l’aide d’une commande semblable à celle-ci :

    New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True

Après avoir créé la stratégie, vous devez l’affecter à tout utilisateur ayant besoin d’accéder au magasin de contacts unifié. Les stratégies par utilisateur peuvent être affectées aux utilisateurs à l’aide de commandes semblables à ce qui suit :

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"

Après avoir affecté la stratégie, Lync Server commence à migrer les contacts de l’utilisateur vers le magasin de contacts unifié. À l’issue de la migration, les contacts de l’utilisateur sont stockés dans Exchange et non dans Lync Server. Si l’utilisateur est connecté à Lync 2013 au moment où la migration se termine, une zone de message s’affiche pour lui demander de se déconnecter de Lync et de se reconnecter afin de finaliser le processus. Les utilisateurs auxquels cette stratégie par utilisateur n'a pas été affectée ne verront pas leurs contacts migrer vers le magasin de contacts unifié. Et ce, car ces utilisateurs sont gérés par la stratégie globale, et l'utilisation du magasin de contacts unifié a été désactivée dans la stratégie globale.

Vous pouvez vérifier que les contacts d’un utilisateur ont bien été migrés vers le magasin de contacts unifié en exécutant l’applet de commande [Test-CsUnifiedContactStore](https://docs.microsoft.com/en-us/powershell/module/skype/Test-CsUnifiedContactStore) à partir de Lync Server Management Shell :

    Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"

Si Test-CsUnifiedContactStore réussit, cela signifie que les contacts de l’utilisateur sip:kenmyer@litwareinc.com ont été migrés vers le magasin de contacts unifié.

## Restauration du magasin de contacts unifié

Si vous souhaitez supprimer les contacts d’un utilisateur du magasin de contacts unifié (par exemple, si l’utilisateur doit être rapatrié sur Microsoft Lync Server 2010 et qu’il ne peut donc plus utiliser le magasin de contacts unifié), vous devez faire deux choses. Premièrement, vous devez affecter à l’utilisateur une nouvelle stratégie de services d’utilisateurs qui interdit le stockage de contacts dans le magasin de contacts unifié (autrement dit, une stratégie où la propriété UcsAllowed a la valeur $False). Si vous ne disposez pas d’une telle stratégie, vous pouvez en créer une à l’aide d’une commande semblable à celle-ci :

    New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False

Vous pouvez ensuite affecter cette nouvelle stratégie par utilisateur (NoUnifiedContactStore) à l’aide d’une commande semblable à celle-ci :

    Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore

La commande précédente affecte la nouvelle stratégie à l’utilisateur Ken Myer et empêche la migration des contacts de Ken vers le magasin de contacts unifié.

> [!NOTE]  
> Dans certains cas, vous pouvez obtenir le même résultat en annulant simplement l’affectation de la stratégie de services d’utilisateurs actuelle de l’utilisateur. Par exemple, supposons que Ken Myer possède une stratégie de services d’utilisateurs par utilisateur qui active le magasin de contacts unifié, alors que votre stratégie globale interdit l’utilisation du magasin de contacts unifié. Dans ce cas, vous pouvez annuler l’affectation de la stratégie de services par utilisateur à Ken. Il est alors automatiquement géré par la stratégie globale et n’a donc plus accès au magasin de contacts unifié.<br />
Pour annuler l’affectation d’une stratégie par utilisateur précédemment affectée, utilisez la même commande que celle indiquée précédemment, mais cette fois en affectant au paramètre PolicyName la valeur Null :<br />
Grant-CsUserServicesPolicy –Identity &quot;Ken Myer&quot; –PolicyName $Null

Lorsque vous travaillez avec le magasin de contacts unifié, il est important de garder à l’esprit que la commande « empêche la migration des contacts de Ken vers le magasin de contacts unifié ». Le simple fait d’affecter une nouvelle stratégie de services d’utilisateurs à Ken ne déplace pas ses contacts hors du magasin de contacts unifié. Lorsqu’un utilisateur se connecte à Lync Server 2013, le système vérifie la stratégie de services d’utilisateurs de l’utilisateur afin de déterminer si ses contacts doivent être conservés dans le magasin de contacts unifié. Dans l’affirmative (c’est-à-dire si la propriété UcsAllowed a la valeur $True), les contacts sont migrés vers le magasin de contacts unifié (en supposant que ces contacts ne se trouvent pas déjà dans le magasin de contacts unifié). Dans la négative, Lync Server ignore simplement les contacts de l’utilisateur et passe à la tâche suivante. Cela signifie que Lync Server ne déplace pas automatiquement les contacts d’un utilisateur hors du magasin de contacts unifié, et ce quelle que soit la valeur de la propriété UcsAllowed.

Ainsi, après avoir affecté une nouvelle stratégie de services d’utilisateurs à l’utilisateur, vous devez exécuter l’applet de commande [Invoke-CsUcsRollback](https://docs.microsoft.com/en-us/powershell/module/skype/Invoke-CsUcsRollback) pour déplacer les contacts de l’utilisateur hors de Exchange 2013 et les faire revenir dans Lync Server 2013. Par exemple, après avoir affecté une nouvelle stratégie de services d’utilisateurs à Ken Myer, vous pouvez déplacer ses contacts hors du magasin de contacts unifié à l’aide de la commande suivante :

    Invoke-CsUcsRollback -Identity "Ken Myer"

Si vous modifiez la stratégie de services d’utilisateurs sans exécuter l’applet de commande Invoke-CsUcsRollback, les contacts de Ken ne sont pas supprimés du magasin de contacts unifié. Que se passe-t-il si vous exécutez Invoke-CsUcsRollback sans modifier la stratégie de services d’utilisateurs de Ken Myer ? Dans ce cas, les contacts de Ken sont temporairement supprimés du magasin de contacts unifié. Il est important de noter que cette suppression est temporaire. Sept jours après la suppression des contacts de Ken du magasin de contacts unifié, Lync Server 2013 vérifie la stratégie des services d’utilisateurs qui a été affectée à Ken. Si une stratégie qui autorise l’utilisation du magasin de contacts unifié est toujours affectée à Ken, ses contacts sont automatiquement replacés dans le magasin de contacts. Pour supprimer définitivement les contacts du magasin de contacts unifié, vous devez non seulement modifier la stratégie de services d’utilisateurs, mais aussi exécuter l’applet de commande Invoke-CsUcsRollback.

Compte tenu du grand nombre de variables pouvant affecter la migration, il est difficile d'estimer le délai nécessaire pour migrer totalement les comptes vers le magasin de contacts unifié. En règle générale, cependant, la migration n'a pas un effet immédiat : même lors de la migration d'un petit nombre de contacts, cela peut prendre 10 minutes au moins avant que le transfert ne se termine.

