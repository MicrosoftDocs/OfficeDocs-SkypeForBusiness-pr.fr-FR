---
title: Configuration de Skype Entreprise Server pour utiliser le magasin de contacts unifié
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
description: 'Résumé : Configurez le magasin de contacts unifié pour Exchange Server et Skype pour Business Server.'
ms.openlocfilehash: 711dd4ea53b9985806833fbe5bc92428116bff23
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26295382"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Configuration de Skype Entreprise Server pour utiliser le magasin de contacts unifié
 
**Résumé :** Configurer le magasin de contacts unifié pour Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server.
  
Les utilisateurs à l’aide du magasin de contacts unifié, mettre à jour une liste de contacts unique et dispose de ces contacts disponibles dans plusieurs applications, y compris Skype pour entreprises, Microsoft Outlook 2013 et Microsoft Outlook Web App 2013. Lorsque vous activez le magasin de contacts unifié pour un utilisateur, que les contacts de l’utilisateur ne sont pas stockées dans Skype pour Business Server et récupérés selon vos besoins. Au lieu de cela, ses contacts sont stockés dans Exchange Server 2016 ou Exchange Server 2013 et sont récupérées à l’aide des Services Web Exchange.
  
> [!NOTE]
> Techniquement, les informations de contact sont stockées dans une paire de dossiers de boîte aux lettres Exchange de l’utilisateur. Les contacts eux-mêmes sont stockés dans un dossier nommé Skype pour Contacts professionnels qui est visible pour les utilisateurs ; métadonnées sur les contacts sont stockés dans un sous-dossier qui n’est pas visible par les utilisateurs finaux. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Activation du magasin de contacts unifié pour un utilisateur

Si l’authentification de serveur à serveur entre Skype pour Business Server et Exchange Server est déjà configurée, puis vous avez également activé le magasin de contacts unifié ; Aucune configuration de serveur supplémentaire est requise. Cependant, il est nécessaire de configurer des comptes utilisateur supplémentaires pour déplacer les contacts d’un utilisateur dans le magasin de contacts unifié. Par défaut, les contacts de l’utilisateur sont conservés dans Skype pour Business Server et non dans le magasin de contacts unifié.
  
Accès au magasin de contacts unifié est géré à l’aide de Skype pour les stratégies des services Business Server utilisateur. Les stratégies de services d’utilisateurs ne possèdent qu’une seule propriété (UcsAllowed) ; celle-ci permet de déterminer l’emplacement dans lequel les contacts de l’utilisateur sont stockés. Si un utilisateur est géré par une stratégie de services d’utilisateurs où UcsAllowed a la valeur True ($True), les contacts de l’utilisateur sont stockés dans le magasin de contacts unifié. Si l’utilisateur est géré par stratégie où paramètre UcsAllowed a la valeur False ($False), puis ses contacts seront stockés dans Skype pour Business Server de services d’un utilisateur.
  
Lorsque vous installez Skype pour Business Server, une stratégie de services utilisateur unique (configurée dans l’étendue globale) est également installée. La valeur UcsAllowed dans cette stratégie a la valeur True, ce qui signifie que les contacts de l’utilisateur sont stockés par défaut dans le magasin de contacts unifié (en supposant que celui-ci ait été déployé et configuré). Si vous voulez migrer tous vos contacts utilisateurs vers le magasin de contacts unifié, vous n’avez aucune tâche à effectuer. 
  
Si vous préférez ne pas migrer tous vos contacts vers le magasin de contacts unifié, vous pouvez désactiver celui-ci pour tous les utilisateurs en définissant la propriété UcsAllowed de la stratégie globale sur False :
  
```
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Après avoir désactivé le magasin de contacts unifié dans la stratégie globale vous pouvez ensuite créer une stratégie d’utilisateur qui permet d’utiliser le magasin de contacts unifié ; Cela vous permet de conserver leurs contacts dans le magasin de contacts unifié alors que les autres utilisateurs continuent à conserver leurs contacts dans Skype pour Business Server à certains utilisateurs. Vous pouvez créer une stratégie de services utilisateur par utilisateur à l’aide d’une commande similaire à celle-ci :
  
```
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Après avoir créé la stratégie, vous devez l’affecter à tout utilisateur ayant besoin d’accéder au magasin de contacts unifié. Les stratégies par utilisateur peuvent être affectées aux utilisateurs à l’aide de commandes semblables à ce qui suit :
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Une fois que la stratégie a été affectée, Skype pour Business Server commencera à migrer des contacts de l’utilisateur vers le magasin de contacts unifié. Une fois la migration est terminée, l’utilisateur aura puis ses contacts stockées dans Exchange au lieu de Skype pour Business Server. Si l’utilisateur est connecté à Lync 2013 à la migration de temps est terminée, une boîte de message s’affiche et qu’il sera invitée à vous déconnecter de Skype pour les entreprises et se reconnecter pour finaliser le processus. Les utilisateurs auxquels cette stratégie par utilisateur n’a pas été affectée ne verront pas leurs contacts migrer vers le magasin de contacts unifié. C’est parce que ces utilisateurs sont gérés par la stratégie globale, et utiliser le magasin de contacts unifié a été désactivé dans la stratégie globale.
  
Vous pouvez vérifier que les contacts d’un utilisateur ont été migrés vers le magasin de contacts unifié en exécutant l’applet de commande [Test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) à partir de la Skype pour Business Server Management Shell :
  
```
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Si le Test-CsUnifiedContactStore réussit, cela signifie que les contacts pour l’utilisateur sip : kenmyer @<span></span>litwareinc<span></span>.com ont été migrés vers le magasin de contacts unifié.
  
## <a name="rolling-back-the-unified-contact-store"></a>Restauration du magasin de contacts unifié

Si vous devez supprimer des contacts d’un utilisateur à partir du magasin de contacts unifié (par exemple, si l’utilisateur doit être migrés sur Microsoft Lync Server 2010 et par conséquent ne peut plus utiliser le magasin de contacts unifié), vous devez effectuer deux opérations. Tout d’abord, vous devez attribuer à l’utilisateur une nouvelle stratégie de services utilisateur, qui empêche le stockage des contacts dans le magasin de contacts unifié. (C'est-à-dire, une stratégie où la propriété du paramètre UcsAllowed a été défini sur $False.) Si vous n’avez pas une telle stratégie, vous pouvez créer à l’aide d’une commande similaire à celle-ci :
  
```
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Vous pouvez ensuite affecter cette nouvelle stratégie par utilisateur (NoUnifiedContactStore) à l’aide d’une commande semblable à celle-ci :
  
```
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

La commande précédente affecte la nouvelle stratégie à l’utilisateur Ken Myer et empêche la migration des contacts de Ken vers le magasin de contacts unifié.
  
> [!NOTE]
> Dans certains cas, vous pouvez obtenir le même résultat en annulant simplement l’affectation de la stratégie de services d’utilisateurs actuelle de l’utilisateur. Par exemple, supposons que Ken Myer possède une stratégie de services d’utilisateurs par utilisateur qui active le magasin de contacts unifié, alors que votre stratégie globale interdit l’utilisation du magasin de contacts unifié. Dans ce cas, vous pouvez annuler l’affectation de la stratégie de services par utilisateur à Ken. Il est alors automatiquement géré par la stratégie globale et n’a donc plus accès au magasin de contacts unifié. Pour Désattribuer précédemment affectés par utilisateur et la stratégie, utilisez la même commande comme avant, mais cette fois définissez le paramètre PolicyName sur une valeur null : Grant-CsUserServicesPolicy-Identity « Ken Myer » - PolicyName $Null 
  
Lorsque vous travaillez avec le magasin de contacts unifié, il est important de garder à l’esprit que la commande « empêche la migration des contacts de Ken vers le magasin de contacts unifié ». Le simple fait d’affecter une nouvelle stratégie de services d’utilisateurs à Ken ne déplace pas ses contacts hors du magasin de contacts unifié. Lorsqu’un utilisateur ouvre une session sur Skype pour Business Server, le système vérifie la stratégie de services utilisateur de l’utilisateur pour voir si ses contacts doivent être conservées dans le magasin de contacts unifié. Si la réponse est oui (c’est-à-dire si la propriété UcsAllowed a la valeur $True), les contacts sont migrés vers le magasin de contacts unifié (en supposant que ces contacts ne se trouvent pas déjà dans le magasin de contacts unifié). Si la réponse est non, puis Skype pour Business Server ignore les contacts de l’utilisateur et passe à la tâche suivante. Cela signifie que Skype pour Business Server automatiquement ne déplacera pas les contacts d’un utilisateur d’un magasin de contacts unifié, quelle que soit la valeur de la propriété du paramètre UcsAllowed.
  
Cela signifie également que, après avoir attribué à l’utilisateur une nouvelle stratégie de services utilisateur, vous devez ensuite exécuter l’applet de commande [Invoke-csucsrollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) n’afin de déplacer les contacts de l’utilisateur en dehors d’Exchange Server, puis sur Skype pour Business Server. Par exemple, après avoir affecté une nouvelle stratégie de services d’utilisateurs à Ken Myer, vous pouvez déplacer ses contacts hors du magasin de contacts unifié à l’aide de la commande suivante :
  
```
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Si vous modifiez la stratégie de services d’utilisateurs sans exécuter l’applet de commande Invoke-CsUcsRollback, les contacts de Ken ne sont pas supprimés du magasin de contacts unifié. Que se passe-t-il si vous exécutez Invoke-CsUcsRollback sans modifier la stratégie de services d’utilisateurs de Ken Myer ? Dans ce cas, les contacts de Ken sont temporairement supprimés du magasin de contacts unifié. Il est important de noter que cette suppression est temporaire. Après la suppression de contacts de Ken à partir du magasin de contacts unifié, Skype pour Business Server s’attendre sept jours et puis vérifier la stratégie de services utilisateur a été affectée à Ken. Si une stratégie qui autorise l’utilisation du magasin de contacts unifié est toujours affectée à Ken, ses contacts sont automatiquement replacés dans le magasin de contacts. Pour supprimer définitivement les contacts du magasin de contacts unifié, vous devez non seulement modifier la stratégie de services d’utilisateurs, mais aussi exécuter l’applet de commande Invoke-CsUcsRollback.
  
Compte tenu du grand nombre de variables pouvant affecter la migration, il est difficile d’estimer le délai nécessaire pour migrer totalement les comptes vers le magasin de contacts unifié. En règle générale, cependant, la migration n’a pas un effet immédiat : même lors de la migration d’un petit nombre de contacts, cela peut prendre 10 minutes au moins avant la fin du transfert.
  

