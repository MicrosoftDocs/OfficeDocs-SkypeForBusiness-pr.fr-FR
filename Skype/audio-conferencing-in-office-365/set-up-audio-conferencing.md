---
title: "Configurer la conférence Audio pour Skype entreprise et Teams Microsoft"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: d01954f1-4f37-4cf5-a636-20039e5c59e9
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business, Microsoft Teams
localization_priority: Normal
ROBOTS: None
f1keywords: O365P_DialInConfDesc
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
- LIL_Placement
description: "Apprenez à configurer les conférences audio ou accès à distance pour les personnes de votre entreprise qui ont besoin de joindre des conférences téléphoniques à l’aide d’un téléphone. "
ms.openlocfilehash: 6d8fae08a5dc8e6a1cf6bc05b458840c47fc83ed
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/15/2017
---
# <a name="set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams"></a>Configurer la conférence Audio pour Skype entreprise et Teams Microsoft

Les personnes de votre organisation devez parfois utiliser un téléphone pour appeler une réunion. Skype pour les entreprises et les Teams Microsoft incluent la fonctionnalité de conférence audio seulement cette situation ! Personnes peut appeler Skype pour les réunions d’entreprise ou Teams de Microsoft à l’aide d’un téléphone, au lieu d’utiliser le Skype pour une application métier ou Teams de Microsoft sur un PC ou un périphérique mobile. 
  
Vous devez uniquement configurer d’Audio conférence pour les personnes qui souhaitent planifier ou de mener des réunions. Participants à la réunion qui se connectent en n’avez pas besoin des licences attribuées ou autre programme d’installation.
  
Pour les questions fréquemment posées à propos des conférences de données Audio, consultez [questions courantes d’audioconférence](audio-conferencing-common-questions.md).
  
## <a name="step-1-buy-and-assign-licenses"></a>Étape 1 : Acheter et attribuer des licences
<a name="__top"> </a>

Vous devez être un [sur Office 365 rôles d’administrateur](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) pour effectuer cette étape.
  
1. Découvrez si audioconférence dans Office 365 est disponible dans votre pays/région. [Pays et région de disponibilité pour les conférences Audio et les Plans d’appel](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md). 
    
2. Découvrez les licences que vous devez acheter pour les conférences Audio et comment leur coût. Voir [Skype pour les professionnels et les équipes Microsoft module complémentaire Gestionnaire de licences](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)et acheter les licences. 
    
3. [Attribuer ou supprimer des licences pour Office 365 pour entreprises](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) , vous avez acheté aux personnes de votre organisation qui s’apprêtent à des réunions de planification ou de prospect.
    
4. Si vous avez acheté des licences de module complémentaire **Audioconférence** et crédits de la communication, les affecter trop. Pour obtenir des instructions, reportez-vous à la section [Affecter un Skype pour les professionnels et les équipes Microsoft des licences](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).
    
## <a name="step-2-decide-on-your-audio-conferencing-provider"></a>Étape 2 : Choisissez votre fournisseur de conférence audio
<a name="__top"> </a>

Un fournisseur de conférence audio fournit un *pont de conférence audio*. Le pont de conférence définit les numéros de téléphone, broches, les ID de conférence pour les réunions. Décider s’il faut utiliser Microsoft ou un fournisseur de conférence audio de tiers :
  
> [!NOTE]
> Les utilisateurs de Microsoft Teams ne peut pas utilisateur d’un fournisseur de conférence audio de tiers. 
  
- **Microsoft en tant que votre fournisseur de conférence audio**: Si vous souhaitez que la solution la plus simple pour les conférences audio, choisissez Microsoft en tant que votre fournisseur de conférence audio.
    
- **Tiers en tant que votre fournisseur de conférence audio**: Si vous êtes dans un pays où la conférence Audio dans Office 365 n’est pas disponible, la qualité de service n’est pas idéale en raison de son emplacement ou vous avez un contrat existant, choisissez un audio tiers fournisseur de la conférence. Pour rechercher un fournisseur, accédez à [Microsoft PinPoint](http://go.microsoft.com/fwlink/?LinkId=797530).
    
> [!TIP]
> Dans votre organisation, vous pouvez avoir certains utilisateurs de Microsoft comme leur fournisseur de conférence audio, les personnes qui utilisent un fournisseur tiers. Mais cela sera plus complexe, vous pouvez configurer et gérer. 
  
Pour une comparaison détaillée entre Microsoft comme fournisseur audio et d’un fournisseur tiers, consultez [comparaison de fournisseurs de conférence audio](compare-audio-conferencing-providers.md). 
  
## <a name="step-3-assign-the-audio-conferencing-provider-to-people-who-lead-or-schedule-meetings"></a>Étape 3 : Affectez le fournisseur de conférence audio pour les personnes qui avance ou planifient des réunions
<a name="__top"> </a>

Maintenant que vous avez choisi votre fournisseur de conférence audio, vous devez affecter le fournisseur à des personnes de votre organisation qui avance ou planifier des réunions. Effectuez l’une des actions suivantes : 
  
- [Affectation de Microsoft en tant que le fournisseur de conférence audio](assign-microsoft-as-the-audio-conferencing-provider.md).
    
- [Affecter un comme fournisseur de conférence audio tiers](assign-a-third-party-as-the-audio-conferencing-provider.md).
    
## <a name="step-4-set-up-meeting-invitations"></a>Étape 4 : Définir des invitations à une réunion
<a name="__top"> </a>

Les étapes suivantes sont **facultatives**, mais beaucoup d’administrateurs comme les exécuter :
  
1. [Invitations à personnaliser](../set-up-skype-for-business-online/customize-meeting-invitations.md). Les numéros d’accès à distance sont définies pour l’utilisateur seront automatiquement ajoutés aux invitations à la réunion sont envoyées aux participants. Toutefois, vous pouvez ajouter votre propre aide et liens juridiques, un message texte et graphique de petite entreprise.
    
2. [Jeu de numéros de téléphone Audio conférence pour les organisateurs qui sont inclus dans les invitations de réunion](set-the-phone-numbers-included-on-invites.md). C’est le numéro de téléphone qui s’affiche lors de la réunion est planifiée par l’utilisateur.
    
3. Pour [définir les langues de surveillance automatique pour les conférences Audio](set-auto-attendant-languages-for-audio-conferencing.md) la surveillance automatique de conférence audio utilise pour accueillir un appelant lorsqu’ils se connectent à un numéro de téléphone de conférence Audio. Cette étape s’applique uniquement si vous utilisez Microsoft comme fournisseur audio.
    
4. [Définir la longueur de la broche pour les réunions de la conférence de l’Audio](set-the-pin-length-for-audio-conferencing-meetings.md).
    
> [!NOTE]
> Cette fonctionnalité n’est pas encore disponible pour les clients à l’aide d’Office 365 exploités par 21Vianet en Chine. Pour plus d’informations, reportez-vous à la section [en savoir plus sur Office 365 exploités par 21Vianet](https://support.office.com/article/A8AB5061-3346-4DA0-BB7C-5260822B53AE). 
  
[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
   
## <a name="related-topics"></a>Rubriques connexes

[Questions courantes des conférences audio](audio-conferencing-common-questions.md)
  
[Configurer Skype Entreprise Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
  
[Numéros de téléphone pour les conférences Audio](phone-numbers-for-audio-conferencing.md)
  
[Définir des options pour les réunions en ligne et des conférences téléphoniques](https://support.office.com/article/DCD1CA39-0C1F-466C-9573-F04138FEF5E2)

