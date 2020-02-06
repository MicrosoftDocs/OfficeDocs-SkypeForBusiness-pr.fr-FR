---
title: Configuration de Skype Entreprise Server pour utiliser le magasin de contacts unifié
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/7/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 6aa17ae3-764e-4986-a900-85a3cdb8c1fc
description: 'Résumé : configurez le magasin de contacts unifié pour Exchange Server et Skype entreprise Server.'
ms.openlocfilehash: 1719b8e8e5d99b8ef24da32111b69b1f9f847538
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796995"
---
# <a name="configure-skype-for-business-server-to-use-the-unified-contact-store"></a>Configuration de Skype Entreprise Server pour utiliser le magasin de contacts unifié
 
**Résumé :** Configurez le magasin de contacts unifié pour Exchange Server 2016 ou Exchange Server 2013 et Skype entreprise Server.
  
À l’aide du magasin de contacts unifié, les utilisateurs conservent une seule liste de contacts et disposent de ces contacts dans plusieurs applications, dont Skype entreprise, Microsoft Outlook 2013 et Microsoft Outlook Web App 2013. Lorsque vous activez le magasin de contacts unifié pour un utilisateur, ses contacts ne sont pas stockés dans Skype entreprise Server et sont récupérés selon les besoins. Au lieu de cela, ses contacts sont stockés dans Exchange Server 2016 ou Exchange Server 2013 et sont récupérés à l’aide des services Web Exchange.
  
> [!NOTE]
> Techniquement, les informations de contact sont stockées dans une paire de dossiers de la boîte aux lettres Exchange de l’utilisateur. Les contacts eux-mêmes sont stockés dans un dossier intitulé contacts Skype entreprise visible par les utilisateurs finaux. les métadonnées relatives aux contacts sont stockées dans un sous-dossier qui n’est pas visible pour les utilisateurs finaux. 
  
## <a name="enabling-the-unified-contact-store-for-a-user"></a>Activation du magasin de contacts unifié pour un utilisateur

Si l’authentification de serveur à serveur entre Skype entreprise Server et Exchange Server est déjà configurée, vous avez également activé le magasin de contacts unifié ; aucune configuration serveur supplémentaire n’est requise. Cependant, il est nécessaire de configurer des comptes utilisateur supplémentaires pour déplacer les contacts d’un utilisateur dans le magasin de contacts unifié. Par défaut, les contacts de l’utilisateur sont conservés dans Skype entreprise Server et non dans le magasin de contacts unifié.
  
L’accès au magasin de contacts unifié est géré à l’aide de stratégies de services d’utilisateurs Skype entreprise Server. Les stratégies de services d’utilisateurs ne possèdent qu’une seule propriété (UcsAllowed) ; celle-ci permet de déterminer l’emplacement dans lequel les contacts de l’utilisateur sont stockés. Si un utilisateur est géré par une stratégie de services d’utilisateur où UcsAllowed a été défini sur true ($True), les contacts de l’utilisateur seront stockés dans le magasin de contacts unifié. Si l’utilisateur est géré par une stratégie de services d’utilisateur où UcsAllowed a été défini sur false ($False), ses contacts seront stockés dans Skype entreprise Server.
  
Lorsque vous installez Skype entreprise Server, une stratégie de services d’utilisateur unique (configurée au niveau de l’étendue globale) est également installée. La valeur UcsAllowed dans cette stratégie a la valeur True, ce qui signifie que les contacts de l’utilisateur sont stockés par défaut dans le magasin de contacts unifié (en supposant que celui-ci ait été déployé et configuré). Si vous voulez migrer tous vos contacts utilisateurs vers le magasin de contacts unifié, vous n’avez aucune tâche à effectuer. 
  
Si vous préférez ne pas migrer tous vos contacts vers le magasin de contacts unifié, vous pouvez désactiver celui-ci pour tous les utilisateurs en définissant la propriété UcsAllowed de la stratégie globale sur False :
  
```powershell
Set-CsUserServicesPolicy -Identity global -UcsAllowed $False
```

Après avoir désactivé le magasin de contacts unifié dans la stratégie globale, vous pouvez créer une stratégie par utilisateur qui permet d’utiliser le magasin de contacts unifié ; Cela vous permet de faire en sorte que certains utilisateurs gardent leurs contacts dans le magasin de contacts unifié tandis que d’autres utilisateurs continuent à conserver leurs contacts dans Skype entreprise Server. Vous pouvez créer une stratégie de services utilisateur par utilisateur à l’aide d’une commande similaire à celle-ci :
  
```powershell
New-CsUserServicesPolicy -Identity "AllowUnifiedContactStore" -UcsAllowed $True
```

Après avoir créé la stratégie, vous devez l’affecter à tout utilisateur ayant besoin d’accéder au magasin de contacts unifié. Les stratégies par utilisateur peuvent être affectées aux utilisateurs à l’aide de commandes semblables à ce qui suit :
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName "AllowUnifiedContactStore"
```

Une fois la stratégie attribuée, Skype entreprise Server commence à migrer les contacts de l’utilisateur dans le magasin de contacts unifié. Une fois la migration terminée, l’utilisateur a alors ses contacts stockés dans Exchange plutôt que dans Skype entreprise Server. Si l’utilisateur est connecté à Lync 2013 au terme de la migration, un message s’affiche et il sera invité à se déconnecter de Skype entreprise, puis à se reconnecter pour finaliser le processus... Les utilisateurs auxquels cette stratégie par utilisateur n’a pas été affectée ne verront pas leurs contacts migrer vers le magasin de contacts unifié. En effet, les utilisateurs gérés par la politique globale et utilisant le magasin de contacts unifié ont été désactivés dans la stratégie globale.
  
Vous pouvez vérifier que les contacts d’un utilisateur ont bien été déplacés vers le magasin de contacts unifié en exécutant l’applet de [contrôle de test-CsUnifiedContactStore](https://docs.microsoft.com/powershell/module/skype/test-csunifiedcontactstore?view=skype-ps) à partir de Skype entreprise Server Management Shell :
  
```powershell
Test-CsUnifiedContactStore -UserSipAddress "sip:kenmyer@litwareinc.com" -TargetFqdn "atl-cs-001.litwareinc.com"
```

Si test-CsUnifiedContactStore réussit, cela signifie que les contacts de l’utilisateur SIP :<span></span>kenmyer@<span></span>litwareinc. com ont migré vers le magasin de contacts unifié.
  
## <a name="rolling-back-the-unified-contact-store"></a>Restauration du magasin de contacts unifié

Si vous avez besoin de supprimer les contacts d’un utilisateur du magasin de contacts unifié (par exemple, si l’utilisateur doit être rapatrié sur Microsoft Lync Server 2010 et ne peut donc plus utiliser le magasin de contacts unifié), vous devez effectuer deux opérations. Tout d’abord, vous devez affecter à l’utilisateur une nouvelle stratégie de services d’utilisateur, qui empêche le stockage de contacts dans le magasin de contacts unifié. (Il s’agit d’une stratégie dans laquelle la propriété UcsAllowed a été définie sur $False.) Si vous n’avez pas de telle stratégie, vous pouvez en créer une à l’aide d’une commande similaire à celle-ci :
  
```powershell
New-CsUserServicesPolicy -Identity NoUnifiedContactStore -UcsAllowed $False
```

Vous pouvez ensuite affecter cette nouvelle stratégie par utilisateur (NoUnifiedContactStore) à l’aide d’une commande semblable à celle-ci :
  
```powershell
Grant-CsUserServicesPolicy -Identity "Ken Myer" -PolicyName NoUnifiedContactStore
```

La commande précédente affecte la nouvelle stratégie à l’utilisateur Ken Myer et empêche la migration des contacts de Ken vers le magasin de contacts unifié.
  
> [!NOTE]
> Dans certains cas, vous pouvez obtenir le même résultat en annulant simplement l’affectation de la stratégie de services d’utilisateurs actuelle de l’utilisateur. Par exemple, supposons que Ken Myer possède une stratégie de services d’utilisateurs par utilisateur qui active le magasin de contacts unifié, alors que votre stratégie globale interdit l’utilisation du magasin de contacts unifié. Dans ce cas, vous pouvez annuler l’affectation de la stratégie de services par utilisateur à Ken. Il est alors automatiquement géré par la stratégie globale et n’a donc plus accès au magasin de contacts unifié. Pour désactiver une stratégie par utilisateur déjà attribuée, utilisez la même commande que celle présentée précédemment, mais cette fois définissez le paramètre PolicyName sur une valeur NULL : Grant-CsUserServicesPolicy-Identity "Ken Myer"-PolicyName $Null 
  
Lorsque vous travaillez avec le magasin de contacts unifié, il est important de garder à l’esprit que la commande « empêche la migration des contacts de Ken vers le magasin de contacts unifié ». Le simple fait d’affecter une nouvelle stratégie de services d’utilisateurs à Ken ne déplace pas ses contacts hors du magasin de contacts unifié. Lorsqu’un utilisateur se connecte à Skype entreprise Server, le système vérifie la stratégie des services des utilisateurs pour voir si ses contacts doivent être conservés dans le magasin de contacts unifié. Si la réponse est oui (c’est-à-dire si la propriété UcsAllowed a la valeur $True), les contacts sont migrés vers le magasin de contacts unifié (en supposant que ces contacts ne se trouvent pas déjà dans le magasin de contacts unifié). Si la réponse est non, Skype entreprise Server ignore simplement les contacts de l’utilisateur et passe à sa tâche suivante. Cela signifie que Skype entreprise Server ne déplace pas automatiquement les contacts d’un utilisateur du magasin de contacts unifié, quelle que soit la valeur de la propriété UcsAllowed.
  
Par ailleurs, une fois que vous avez attribué à l’utilisateur une nouvelle stratégie de services d’utilisateur, vous devez exécuter l’applet de commande [Invoke-CsUcsRollback](https://docs.microsoft.com/powershell/module/skype/invoke-csucsrollback?view=skype-ps) pour déplacer les contacts de l’utilisateur à partir du serveur Exchange et retourner à Skype entreprise Server. Par exemple, après avoir affecté une nouvelle stratégie de services d’utilisateurs à Ken Myer, vous pouvez déplacer ses contacts hors du magasin de contacts unifié à l’aide de la commande suivante :
  
```powershell
Invoke-CsUcsRollback -Identity "Ken Myer"
```

Si vous modifiez la stratégie de services d’utilisateurs sans exécuter l’applet de commande Invoke-CsUcsRollback, les contacts de Ken ne sont pas supprimés du magasin de contacts unifié. Que se passe-t-il si vous exécutez Invoke-CsUcsRollback sans modifier la stratégie de services d’utilisateurs de Ken Myer ? Dans ce cas, les contacts de Ken sont temporairement supprimés du magasin de contacts unifié. Il est important de noter que cette suppression est temporaire. Après la suppression des contacts de Ken du magasin de contacts unifié, Skype entreprise Server attend 7 jours, puis vérifie la politique de services des utilisateurs qui a été attribuée à Ken. Si une stratégie qui autorise l’utilisation du magasin de contacts unifié est toujours affectée à Ken, ses contacts sont automatiquement replacés dans le magasin de contacts. Pour supprimer définitivement les contacts du magasin de contacts unifié, vous devez non seulement modifier la stratégie de services d’utilisateurs, mais aussi exécuter l’applet de commande Invoke-CsUcsRollback.
  
Compte tenu du grand nombre de variables pouvant affecter la migration, il est difficile d’estimer le délai nécessaire pour migrer totalement les comptes vers le magasin de contacts unifié. En règle générale, cependant, la migration n’a pas un effet immédiat : même lors de la migration d’un petit nombre de contacts, cela peut prendre 10 minutes au moins avant la fin du transfert.
  

