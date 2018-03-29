---
title: Configuration d’une participation aux réunions sans code confidentiel dans Skype Entreprise Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Résumé : Apprenez à configurer la broche sans option de jointure dans Skype pour Business Server 2015 de réunion.'
ms.openlocfilehash: 6e9e26f856fec85b3f7436684d1b084eb3873ba9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a>Configuration d’une participation aux réunions sans code confidentiel dans Skype Entreprise Server
 
**Résumé :** Apprenez à configurer la broche sans option de jointure dans Skype pour Business Server 2015 de réunion.
  
Lorsqu’un appelant d’accès à distance tente de joindre une réunion, le service de conférence Standard automatique (TCHA) place l’appelant un stylet d’exploitation qui est différente de la salle d’attente & #x 2014 ; Si un présentateur n’est pas déjà sur un appel et l’appelant à distance n’a pas entré un code confidentiel du leader. L’option de participation à une réunion sans code confidentiel autorise les appelants à participer à une téléconférence sans entrer de code d’organisateur même s’ils sont les premiers à rejoindre un appel. 
  
Lors de la configuration de cette fonctionnalité, rappelez-vous des points suivants :
  
- Cette option n’est valable que pour les réunions privées.
    
- Elle permet aux appelants RTC de rester dans des réunions privées sans qu’un utilisateur authentifié ne soit présent.
    
- Une fois le paramètre modifié, il s’applique à toutes les nouvelles réunions privées et aux réunions privées existantes.
    
- Il peut être activé sur le site de l’organisateur ou au niveau global.
    
- Les options permettant de définir qui peut contourner la salle d’attente sont les suivantes : 
    
  - **Tous les appelants venant de mon organisation sont admis directement**
    
  - **N’importe quel autre appelant (aucune restriction) est admis directement** (il s’agit du paramètre par défaut).
    
- Lorsque la participation sans code confidentiel est activée, le service CAA invite quand même à entrer un code d’organisateur. Les utilisateurs peuvent participer à la réunion en saisissant ou non un code. Cependant, en conservant la possibilité d’entrer un code confidentiel du leader permet à un appelant d’accès à distance s’authentifier en tant que leader et de gérer la réunion si nécessaire.
    
## <a name="configure-pin-less-meeting-join"></a>Configurer la participation à la réunion sans code confidentiel

Pour activer la jointure sans code PIN réunion pour vos utilisateurs, vous devez utiliser l’applet de commande [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) avec le paramètre AllowAnonymousPstnActivation comme suit :
  
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
  

