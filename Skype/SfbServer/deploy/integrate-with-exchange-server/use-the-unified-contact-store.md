---
title: Configurer Skype Entreprise Server pour utiliser le magasin de contacts unifié
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: 'Résumé : Configurez le magasin de contacts unifié pour Exchange Server et Skype Entreprise Server.'
ms.openlocfilehash: ed28f57350e2ce1d7ed5f92d712bdf5ecc7f3de4
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853668"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Configurer Skype Entreprise Server pour utiliser le magasin de contacts unifié
 
**Résumé :** Configurez le magasin de contacts unifié pour Exchange Server 2016 ou Exchange Server 2013 et Skype Entreprise Server.
  
À l’aide du magasin de contacts unifié, les utilisateurs conservent une seule liste de contacts, puis les ont disponibles dans plusieurs applications, notamment Skype Entreprise, Microsoft Outlook 2013 et Microsoft Outlook Web App 2013. Lorsque vous activez le magasin de contacts unifié pour un utilisateur, les contacts de cet utilisateur ne sont pas stockés dans Skype Entreprise Server et récupérés si nécessaire. Au lieu de cela, ses contacts sont stockés dans Exchange Server 2016 ou Exchange Server 2013 et sont récupérés à l’aide Exchange Services Web.
  
> [!NOTE]
> Techniquement, les informations de contact sont stockées dans deux dossiers trouvés dans la boîte aux lettres Exchange’utilisateur. Les contacts eux-mêmes sont stockés dans un dossier nommé Skype Entreprise contacts visibles par les utilisateurs finaux ; les métadonnées sur les contacts sont stockées dans un sous-foldeur qui n’est pas visible pour les utilisateurs finaux. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Activation du magasin de contacts unifié pour un utilisateur

Si l’authentification de serveur à serveur entre Skype Entreprise Server et Exchange Server est déjà configurée, vous avez également activé le magasin de contacts unifié . aucune configuration serveur supplémentaire n’est requise. Cependant, il est nécessaire de configurer des comptes utilisateur supplémentaires pour déplacer les contacts d’un utilisateur dans le magasin de contacts unifié. Par défaut, les contacts utilisateur sont conservés Skype Entreprise Server et non dans le magasin de contacts unifié.
  
L’accès au magasin de contacts unifié est géré à l’aide de stratégies Skype Entreprise Server services d’utilisateurs. Les stratégies de services d’utilisateurs ne possèdent qu’une seule propriété (UcsAllowed) ; celle-ci permet de déterminer l’emplacement dans lequel les contacts de l’utilisateur sont stockés. Si un utilisateur est géré par une stratégie de services d’utilisateurs où UcsAllowed a été définie sur True ($True), les contacts de l’utilisateur sont stockés dans le magasin de contacts unifié. Si l’utilisateur est géré par une stratégie de services d’utilisateurs où UcsAllowed a été définie sur False ($False), ses contacts sont stockés dans Skype Entreprise Server.
  
Lorsque vous installez Skype Entreprise Server, une stratégie de services d’utilisateur unique (configurée au niveau de l’étendue globale) est également installée. La valeur UcsAllowed dans cette stratégie est définie sur True, ce qui signifie que, par défaut, les contacts utilisateur sont stockés dans le magasin de contacts unifié (en supposant que cela a été déployé et configuré). Si vous souhaitez migrer tous vos contacts utilisateur vers le magasin de contacts unifié, vous n’avez rien à faire du tout. 
  
Si vous préférez ne pas migrer tous vos contacts vers le magasin de contacts unifié, vous pouvez désactiver le magasin de contacts unifié pour tous les utilisateurs en fixant la propriété UcsAllowed dans la stratégie globale sur False :
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Après avoir désactivé le magasin de contacts unifié dans la stratégie globale, vous pouvez créer une stratégie par utilisateur qui permet l’utilisation du magasin de contacts unifié . Cela vous permet de faire en sorte que certains utilisateurs conservent leurs contacts dans le magasin de contacts unifié, tandis que d’autres continuent à conserver leurs contacts Skype Entreprise Server. Vous pouvez créer une stratégie de services utilisateur par utilisateur à l’aide d’une commande semblable à celle-ci :
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Après avoir créé la stratégie, vous devez l’affecter à tout utilisateur ayant besoin d’accéder au magasin de contacts unifié. Les stratégies par utilisateur peuvent être affectées aux utilisateurs à l’aide de commandes semblables à ce qui suit :
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Une fois la stratégie affectée, Skype Entreprise Server commence à migrer les contacts de l’utilisateur vers le magasin de contacts unifié. Une fois la migration terminée, les contacts de l’utilisateur sont stockés Exchange au lieu de Skype Entreprise Server. Si l’utilisateur est connecté à Lync 2013 au moment de la fin de la migration, une boîte de message s’affiche et il est invité à se déconnecter de Skype Entreprise puis à se connecter pour finaliser le processus. Les utilisateurs qui n’ont pas été affectés à cette stratégie par utilisateur n’auront pas leurs contacts migrés vers le magasin de contacts unifié. En effet, ces utilisateurs sont gérés par la stratégie globale et l’utilisation du magasin de contacts unifié a été désactivée dans la stratégie globale.
  
Vous pouvez vérifier que les contacts d’un utilisateur ont été correctement migrés vers le magasin de contacts unifié en exécutant l’cmdlet [Test-CsUnifiedContactStore](/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) à partir de l’Skype Entreprise Server Management Shell :
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Si Test-CsUnifiedContactStore réussi, cela signifie que les contacts de l’utilisateur sip:kenmyer@ litwareinc .com ont été migrés vers le magasin de <span></span> <span></span> contacts unifié.
  
## <a name="rolling-back-the-unified-contact-store"></a>Restauration du magasin de contacts unifié

Si vous devez supprimer les contacts d’un utilisateur du magasin de contacts unifié (par exemple, si l’utilisateur doit être retenté sur Microsoft Lync Server 2010 et ne peut donc plus utiliser le magasin de contacts unifié), vous devez faire deux choses. Tout d’abord, vous devez affecter à l’utilisateur une nouvelle stratégie de services d’utilisateurs, qui interdit le stockage des contacts dans le magasin de contacts unifié. (Autrement dit, une stratégie dans laquelle la propriété UcsAllowed a été définie sur $False.) Si vous n’avez pas cette stratégie, vous pouvez en créer une à l’aide d’une commande semblable à celle-ci :
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Vous pouvez ensuite affecter cette nouvelle stratégie par utilisateur (NoUnifiedContactStore) à l’aide d’une commande semblable à celle-ci :
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

La commande précédente affecte la nouvelle stratégie à l’utilisateur Ken Myer et empêche la migration des contacts de Ken vers le magasin de contacts unifié.
  
> [!NOTE]
> Dans certains cas, vous pouvez obtenir le même effet net en dés assignant simplement la stratégie de services utilisateur actuelle de l’utilisateur. Par exemple, supposons que Ken Myer possède une stratégie de services d’utilisateurs par utilisateur qui active le magasin de contacts unifié, alors que votre stratégie globale interdit l’utilisation du magasin de contacts unifié. Dans ce cas, vous pouvez dés assigner la stratégie de services par utilisateur de Ken. Il est alors automatiquement géré par la stratégie globale et n’a donc plus accès au magasin de contacts unifié. Pour annuler l’affectation d’une stratégie utilisateur précédemment affectée, utilisez la même commande que précédemment, mais définissez cette fois le paramètre PolicyName sur une valeur null : Grant-CsUserServicesPolicy -Identity « Ken Myer » -PolicyName $Null 
  
Lorsque vous travaillez avec le magasin de contacts unifié, il est important de garder à l’esprit que la commande « empêche la migration des contacts de Ken vers le magasin de contacts unifié ». Le simple fait d’affecter une nouvelle stratégie de services d’utilisateurs à Ken ne déplace pas ses contacts hors du magasin de contacts unifié. Lorsqu’un utilisateur se connecte à Skype Entreprise Server, le système vérifie la stratégie de services d’utilisateurs de l’utilisateur pour voir si ses contacts doivent être conservés dans le magasin de contacts unifié. Dans l’affirmative (c’est-à-dire si la propriété UcsAllowed a la valeur $True), les contacts sont migrés vers le magasin de contacts unifié (en supposant que ces contacts ne se trouvent pas déjà dans le magasin de contacts unifié). Si la réponse est non, Skype Entreprise Server ignore simplement les contacts de l’utilisateur et passe à la tâche suivante. Cela signifie que Skype Entreprise Server ne déplace pas automatiquement les contacts d’un utilisateur du magasin de contacts unifié, quelle que soit la valeur de la propriété UcsAllowed.
  
Cela signifie également qu’après avoir attribué à l’utilisateur une nouvelle stratégie de services d’utilisateurs, vous devez exécuter l’cmdlet [Invoke-CsUcsRollback](/powershell/module/skype/invoke-csucsrollback?view=skype-ps) afin de déplacer les contacts de l’utilisateur hors de Exchange Server et de revenir à Skype Entreprise Server. Par exemple, après avoir affecté une nouvelle stratégie de services d’utilisateurs à Ken Myer, vous pouvez déplacer ses contacts hors du magasin de contacts unifié à l’aide de la commande suivante :
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Si vous modifiez la stratégie de services d’utilisateurs sans exécuter l’applet de commande Invoke-CsUcsRollback, les contacts de Ken ne sont pas supprimés du magasin de contacts unifié. Que se passe-t-il si vous exécutez Invoke-CsUcsRollback sans modifier la stratégie de services d’utilisateurs de Ken Myer ? Dans ce cas, les contacts de Ken sont temporairement supprimés du magasin de contacts unifié. Il est important de noter que cette suppression est temporaire. Une fois que les contacts de Ken ont été supprimés du magasin de contacts unifié, Skype Entreprise Server attend 7 jours, puis vérifie quelle stratégie de services d’utilisateurs a été attribuée à Ken. Si une stratégie qui autorise l’utilisation du magasin de contacts unifié est toujours affectée à Ken, ses contacts sont automatiquement replacés dans le magasin de contacts. Pour supprimer définitivement les contacts du magasin de contacts unifié, vous devez non seulement modifier la stratégie de services d’utilisateurs, mais aussi exécuter l’applet de commande Invoke-CsUcsRollback.
  
En raison du grand nombre de variables qui peuvent affecter la migration, il est difficile d’estimer le temps qu’il faudra avant que les comptes soient entièrement migrés vers le magasin de contacts unifié. En règle générale, toutefois, la migration ne prend pas effet immédiatement : même lors de la migration d’un petit nombre de contacts, le déplacement peut prendre 10 minutes ou plus.
