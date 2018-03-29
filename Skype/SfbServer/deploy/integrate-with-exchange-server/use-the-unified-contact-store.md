---
title: Configurer Skype pour 2015 de serveur d’entreprise à utiliser le magasin de contacts unifié
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: 'Résumé : Configurer le magasin de contacts unifiée pour 2016 d’Exchange Server ou Exchange Server 2013 et Skype pour Business Server 2015.'
ms.openlocfilehash: 479032425c8a3d2d66bd341f54908a071dd5480d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-skype-for-business-server-2015-to-use-the-unified-contact-store"></a>Configurer Skype pour 2015 de serveur d’entreprise à utiliser le magasin de contacts unifié
 
**Résumé :** Configurer le magasin de contacts unifiée pour 2016 d’Exchange Server ou Exchange Server 2013 et Skype pour Business Server 2015.
  
À l’aide du magasin de contacts unifié, les utilisateurs gérer une liste de contacts unique et dispose de ces contacts sont disponibles dans de multiples applications, y compris Skype pour les entreprises, Microsoft Outlook 2013 et Microsoft Outlook Web App 2013. Lorsque vous activez le magasin de contacts unifié pour un utilisateur, que les contacts de l’utilisateur ne sont pas stockés dans Skype pour Business Server 2015 et récupérés au besoin. Au lieu de cela, son ou ses contacts sont stockés dans 2016 d’Exchange Server ou Exchange Server 2013 et sont récupérées à l’aide des Services Web Exchange.
  
> [!NOTE]
> Techniquement, les informations de contact sont stockées dans une paire de dossiers de boîte aux lettres Exchange de l’utilisateur. Les contacts eux-mêmes sont stockés dans un dossier nommé Skype pour Contacts professionnels qui est visible pour les utilisateurs finaux ; les métadonnées sur les contacts sont stockés dans un sous-dossier qui n’est pas visible aux utilisateurs finaux. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Activation du magasin de contacts unifié pour un utilisateur

Si l’authentification de serveur à serveur entre Skype pour Business Server 2015 et 2016 d’Exchange Server ou Exchange Server 2013 est déjà configurée, puis vous avez également activé le magasin de contacts unifié ; Aucune configuration de serveur supplémentaire est nécessaire. Cependant, il est nécessaire de configurer des comptes utilisateur supplémentaires pour déplacer les contacts d’un utilisateur dans le magasin de contacts unifié. Par défaut, les contacts de l’utilisateur sont conservées dans Skype pour le serveur de l’entreprise et non dans le magasin de contacts unifié.
  
Accès au magasin de contacts unifié est géré à l’aide de Skype pour les stratégies de serveur d’entreprise des services utilisateur. Les stratégies de services d’utilisateurs ne possèdent qu’une seule propriété (UcsAllowed) ; celle-ci permet de déterminer l’emplacement dans lequel les contacts de l’utilisateur sont stockés. Si un utilisateur est géré par une stratégie de services d’utilisateurs où UcsAllowed a la valeur True ($True), les contacts de l’utilisateur sont stockés dans le magasin de contacts unifié. Si l’utilisateur est géré par un utilisateur des services stratégie où UcsAllowed a été définie à False ($False), puis son ou ses contacts seront stockées dans Skype pour Business Server.
  
Lorsque vous installez Skype pour Business Server, une stratégie de services unique d’utilisateur (configurée au niveau de la portée globale) est également installée. La valeur UcsAllowed dans cette stratégie a la valeur True, ce qui signifie que les contacts de l’utilisateur sont stockés par défaut dans le magasin de contacts unifié (en supposant que celui-ci ait été déployé et configuré). Si vous voulez migrer tous vos contacts utilisateurs vers le magasin de contacts unifié, vous n’avez aucune tâche à effectuer. 
  
Si vous préférez ne pas migrer tous vos contacts vers le magasin de contacts unifié, vous pouvez désactiver celui-ci pour tous les utilisateurs en définissant la propriété UcsAllowed de la stratégie globale sur False :
  
```
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Après avoir désactivé le magasin de contacts unifié de la stratégie globale vous pouvez ensuite créer une stratégie d’utilisateur qui permet d’utiliser le magasin de contacts unifié ; Cela vous permet d’avoir à certains utilisateurs de conserver leurs contacts dans le magasin de contacts unifié, tandis que les autres utilisateurs continuent à conserver leurs contacts dans Skype pour Business Server. Vous pouvez créer une stratégie de services utilisateur par utilisateur à l’aide d’une commande similaire à celle-ci :
  
```
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Après avoir créé la stratégie, vous devez l’affecter à tout utilisateur ayant besoin d’accéder au magasin de contacts unifié. Les stratégies par utilisateur peuvent être affectées aux utilisateurs à l’aide de commandes semblables à ce qui suit :
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Une fois que la stratégie a été affectée, Skype pour Business Server commencera à migrer des contacts de l’utilisateur vers le magasin de contacts unifié. Une fois la migration terminée, l’utilisateur aura ensuite ses contacts stockés dans Exchange au lieu de Skype pour Business Server. Si l’utilisateur est connecté à Lync 2013 à la migration de temps est terminée, une boîte de message s’affiche et il sera demandé à se connecter sur Skype pour les entreprises et puis rouvrez une session pour finaliser le processus. Les utilisateurs auxquels cette stratégie par utilisateur n’a pas été affectée ne verront pas leurs contacts migrer vers le magasin de contacts unifié. C’est parce que les utilisateurs sont gérés par la stratégie globale, et utiliser le magasin de contacts unifié a été désactivée dans la stratégie globale.
  
Vous pouvez vérifier que les contacts d’un utilisateur ont été migrés vers le magasin de contacts unifié en exécutant l’applet de commande [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) à partir de la Skype pour Business Server Management Shell :
  
```
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Si Test-CsUnifiedContactStore réussit, cela signifie que les contacts de l’utilisateur sip:kenmyer@litwareinc.com ont été migrés vers le magasin de contacts unifié.
  
## <a name="rolling-back-the-unified-contact-store"></a>Restauration du magasin de contacts unifié

Si vous avez besoin supprimer des contacts d’un utilisateur dans le magasin de contacts unifié (par exemple, si l’utilisateur a besoin d’être rapatriés sur Microsoft Lync Server 2010 et par conséquent ne peut plus utiliser le magasin de contacts unifié), vous devez faire deux choses. Tout d’abord, vous devez affecter à l’utilisateur une nouvelle stratégie de services d’utilisateurs, qui interdit le stockage des contacts dans le magasin de contacts unifié. (C'est-à-dire, une stratégie où la propriété UcsAllowed a été défini sur $False.) Si vous ne disposez pas d’une telle stratégie, vous pouvez créer à l’aide d’une commande similaire à celle-ci :
  
```
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Vous pouvez ensuite affecter cette nouvelle stratégie par utilisateur (NoUnifiedContactStore) à l’aide d’une commande semblable à celle-ci :
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

La commande précédente affecte la nouvelle stratégie à l’utilisateur Ken Myer et empêche la migration des contacts de Ken vers le magasin de contacts unifié.
  
> [!NOTE]
> Dans certains cas, vous pouvez obtenir le même résultat en annulant simplement l’affectation de la stratégie de services d’utilisateurs actuelle de l’utilisateur. Par exemple, supposons que Ken Myer possède une stratégie de services d’utilisateurs par utilisateur qui active le magasin de contacts unifié, alors que votre stratégie globale interdit l’utilisation du magasin de contacts unifié. Dans ce cas, vous pouvez annuler l’affectation de la stratégie de services par utilisateur à Ken. Il est alors automatiquement géré par la stratégie globale et n’a donc plus accès au magasin de contacts unifié. À la stratégie de supprimer l’attribution précédemment affecté par utilisateur, utilisez la même commande comme avant, mais cette fois la valeur du paramètre de stratégie une valeur null : Grant-CsUserServicesPolicy-Identity « Ken Myer » - PolicyName $Null 
  
Lorsque vous travaillez avec le magasin de contacts unifié, il est important de garder à l’esprit que la commande « empêche la migration des contacts de Ken vers le magasin de contacts unifié ». Le simple fait d’affecter une nouvelle stratégie de services d’utilisateurs à Ken ne déplace pas ses contacts hors du magasin de contacts unifié. Lorsqu’un utilisateur ouvre une session sur Skype pour Business Server, le système vérifie la stratégie des services utilisateur de l’utilisateur pour voir si son ou ses contacts doivent être conservées dans le magasin de contacts unifié. Si la réponse est oui (c’est-à-dire si la propriété UcsAllowed a la valeur $True), les contacts sont migrés vers le magasin de contacts unifié (en supposant que ces contacts ne se trouvent pas déjà dans le magasin de contacts unifié). Si la réponse est non, puis Skype pour Business Server ignore les contacts de l’utilisateur et passe à la tâche suivante. Cela signifie que Skype pour Business Server ne déplace pas automatiquement les contacts d’un utilisateur d’un magasin de contacts unifié, indépendamment de la valeur de la propriété UcsAllowed.
  
Cela signifie également que, après avoir attribué à l’utilisateur une nouvelle stratégie de services d’utilisateurs, vous devez ensuite exécuter l’applet de commande [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) pour déplacer des contacts de l’utilisateur Exchange Server et à Skype pour Business Server. Par exemple, après avoir affecté une nouvelle stratégie de services d’utilisateurs à Ken Myer, vous pouvez déplacer ses contacts hors du magasin de contacts unifié à l’aide de la commande suivante :
  
```
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Si vous modifiez la stratégie de services d’utilisateurs sans exécuter l’applet de commande Invoke-CsUcsRollback, les contacts de Ken ne sont pas supprimés du magasin de contacts unifié. Que se passe-t-il si vous exécutez Invoke-CsUcsRollback sans modifier la stratégie de services d’utilisateurs de Ken Myer ? Dans ce cas, les contacts de Ken sont temporairement supprimés du magasin de contacts unifié. Il est important de noter que cette suppression est temporaire. Une fois que les contacts de Ken ont été supprimés du magasin de contacts unifiée, Skype pour Business Server va attendre sept jours, puis vérifiez pour voir quelle stratégie de services utilisateur a été affecté à Ken. Si une stratégie qui autorise l’utilisation du magasin de contacts unifié est toujours affectée à Ken, ses contacts sont automatiquement replacés dans le magasin de contacts. Pour supprimer définitivement les contacts du magasin de contacts unifié, vous devez non seulement modifier la stratégie de services d’utilisateurs, mais aussi exécuter l’applet de commande Invoke-CsUcsRollback.
  
Compte tenu du grand nombre de variables pouvant affecter la migration, il est difficile d’estimer le délai nécessaire pour migrer totalement les comptes vers le magasin de contacts unifié. En règle générale, cependant, la migration n’a pas un effet immédiat : même lors de la migration d’un petit nombre de contacts, cela peut prendre 10 minutes au moins avant la fin du transfert.
  

