---
title: Configurer la réunion sans code confidentiel dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Résumé : Découvrez comment configurer l’option de rejoindre une réunion sans code confidentiel dans Skype Entreprise Server.'
ms.openlocfilehash: 76a2fb401c684e0eb685b733cb1b0a63ecbd9907
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119393"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Configurer la réunion sans code confidentiel dans Skype Entreprise Server
 
**Résumé :** Découvrez comment configurer l’option de rejoindre une réunion sans code confidentiel dans Skype Entreprise Server.
  
Lorsqu’un appelant d’accès tente de participer à une réunion, le service d’Standard automatique de conférence (CAA) place l’appelant dans un stylet différent du &#x2014; de salle d’accueil si un présentateur n’est pas déjà en cours d’appel et que l’appelant n’a pas entré de code confidentiel d’leader. L’option de rejoindre une réunion sans code confidentiel permet aux appelants de participer à une réunion sans entrer de code confidentiel d’leader, même s’ils sont la première personne à participer à un appel. 
  
Gardez à l’esprit les questions suivantes lors de la configuration de cette fonctionnalité :
  
- S’applique uniquement aux réunions privées.
    
- Permet aux appelants PSTN de rester dans des réunions privées sans la présence d’utilisateurs authentifiés.
    
- Une fois le paramètre modifié, il s’applique à toutes les réunions privées existantes et nouvelles.
    
- Peut être activé sur le site de l’organisateur ou au niveau global.
    
- Les options qui peuvent contourner la salle d’entrée peuvent être définies pour l’une des options suivantes : 
    
  - **Tous les membres de mon organisation ayant des appelants entrent directement**
    
  - **Tout le monde (aucune restriction) avec** les appelants entre directement (il s’agit du paramètre par défaut.)
    
- Lorsqu’il est configuré pour activer la jointeur sans code confidentiel, le service CAA demande toujours un code confidentiel d’leader. Les utilisateurs peuvent participer à la réunion, qu’un code confidentiel soit entré ou non. Toutefois, le fait de conserver la possibilité d’entrer un code confidentiel d’leader permet à un appelant de s’authentifier en tant qu’dirigeant et de gérer la réunion si nécessaire.
    
## <a name="configure-pin-less-meeting-join"></a>Configurer la réunion sans code confidentiel

Pour activer la réunion sans code confidentiel pour vos utilisateurs, utilisez l’cmdlet [Set-CsDialInConferencingConfiguration](/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) avec le paramètre AllowAnonymousPstnActivation comme suit :
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Par exemple, la commande suivante active la réunion sans code confidentiel pour le site Redmond :
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Pour des raisons de sécurité, lorsque la réunion sans code confidentiel est désactivée, vous pouvez limiter la numérotation des utilisateurs anonymes en vous assurant que conferencingPolicy est définie comme suit :
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Pour plus d’informations, [voir Set-CsConferencingPolicy](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
