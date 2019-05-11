---
title: Configuration d’une participation aux réunions sans code confidentiel dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Résumé : Découvrez comment configurer le code confidentiel sans option de jointure dans Skype pour Business Server de la réunion.'
ms.openlocfilehash: c865d234b58b29890957a2c895a91d84b9a31bb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33888106"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Configuration d’une participation aux réunions sans code confidentiel dans Skype Entreprise Server
 
**Résumé :** Découvrez comment configurer le code confidentiel sans option de jointure dans Skype pour Business Server de la réunion.
  
Lorsqu’un appelant rendez-vous tente de participer à une réunion, le service de conférence automatique standard (CAA) place l’appelant dans un stylo d’exploitation est différent de la salle d’attente de & #x 2014 ; Si un présentateur n’est pas déjà un appel, et l’appelant entrant n’a pas entré un code confidentiel de l’organisateur. L’option de participation à une réunion sans code confidentiel autorise les appelants à participer à une téléconférence sans entrer de code d’organisateur même s’ils sont les premiers à rejoindre un appel. 
  
Lors de la configuration de cette fonctionnalité, rappelez-vous des points suivants :
  
- Cette option n’est valable que pour les réunions privées.
    
- Elle permet aux appelants RTC de rester dans des réunions privées sans qu’un utilisateur authentifié ne soit présent.
    
- Une fois le paramètre modifié, il s’applique à toutes les nouvelles réunions privées et aux réunions privées existantes.
    
- Il peut être activé sur le site de l’organisateur ou au niveau global.
    
- Les options permettant de définir qui peut contourner la salle d’attente sont les suivantes : 
    
  - **Tous les appelants venant de mon organisation sont admis directement**
    
  - **N’importe quel autre appelant (aucune restriction) est admis directement** (il s’agit du paramètre par défaut).
    
- Lorsque la participation sans code confidentiel est activée, le service CAA invite quand même à entrer un code d’organisateur. Les utilisateurs peuvent participer à la réunion en saisissant ou non un code. Toutefois, en conservant la possibilité d’entrer un code confidentiel du leader permet à un appelant rendez-vous s’authentifier en tant qu’organisateur et la gestion de la réunion, si nécessaire.
    
## <a name="configure-pin-less-meeting-join"></a>Configurer la participation à la réunion sans code confidentiel

Pour permettre de participer à une réunion sans code PIN pour vos utilisateurs, utilisez l’applet de commande [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) avec le paramètre AllowAnonymousPstnActivation comme suit :
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

Par exemple, la commande suivante active une participation sans code confidentiel pour le site Redmond :
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

Pour des raisons de sécurité, lorsque la participation sans code confidentiel est activée, vous souhaiterez peut être empêcher les utilisateurs anonymes d’appeler, en vous assurant que la ConferencingPolicy est définie comme suit :
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

Pour plus d’informations, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).
  

