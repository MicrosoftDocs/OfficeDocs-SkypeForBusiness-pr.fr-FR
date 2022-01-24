---
title: Considérations en rapport avec le PSTN lors de la mise à niveau vers Teams’une Skype Entreprise
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Considérations vocales pour la mise à niveau Skype Entreprise vers Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c19c1860c3a351cd7ed6a6240e20dc253f204ab1
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/24/2022
ms.locfileid: "62180887"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>Considérations en rapport avec le PSTN pour la mise à niveau vers Teams une Skype Entreprise une mise à niveau vers l’ordinateur local

Cet article décrit les considérations concernant le réseau téléphonique commuté (PSTN) lors de la mise à niveau vers Teams.

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

Les articles suivants décrivent les concepts de mise à niveau et les comportements de coexistence importants :

- [Coexistence de Teams et d Skype Entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modes de coexistence - Référence](migration-interop-guidance-for-teams-with-skype.md)
- [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - L’Système téléphonique avec Teams n’est prise en charge que lorsque le compte de l’utilisateur est affecté à une stratégie Teams mise à niveau avec Teams mode uniquement.  
 > - L’Système téléphonique avec Skype Entreprise n’est prise en charge que lorsque le compte de l’utilisateur est affecté à Teams de mise à niveau à l’aide d’un mode SfB. 
 > - Système téléphonique n’est pas pris en charge lorsque le compte de l’utilisateur se voit Teams stratégie de mise à niveau avec le mode Islands.
 > - Les paramètres de passation des appels, de groupe d’appel d’équipe et de délégation d’Skype Entreprise ne sont pas migrés et doivent être recréés pour Teams.
 > - Pour obtenir une vue d’ensemble Microsoft Teams fonctionnalités vocales cloud et vous aider à déterminer la solution vocale Microsoft appropriée pour votre organisation, voir Planifier votre solution Teams [voix.](cloud-voice-landing-page.md)


## <a name="pstn-calling-scenarios"></a>Scénarios d’appel PSTN

Il existe quatre scénarios d’appel possibles lors du passage en mode TeamsOnly :

- [Un utilisateur dans Skype Entreprise Online, avec un plan d’appels Microsoft.](#from-skype-for-business-online-with-microsoft-calling-plans) Lors de la mise à niveau, cet utilisateur continuera à avoir une offre Microsoft Calling.

- [Un utilisateur dans Skype Entreprise Online,](#from-skype-for-business-online-with-on-premises-voice) avec des fonctionnalités vocales en local via Skype Entreprise version en local ou Cloud Connector. Pour vous assurer que l’utilisateur TeamsOnly dispose de la fonctionnalité PSTN, vous devez coordonner la mise à niveau de l’utilisateur vers Teams avec la migration de l’utilisateur vers le routage direct.

- [Un utilisateur sur Skype Entreprise](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)sur site avec Voix Entreprise, qui passe à la connexion en ligne et maintient la connectivité RSTN sur site.  Pour migrer cet utilisateur vers Teams, vous devez déplacer son compte Skype Entreprise local vers le cloud et coordonner le déplacement de l’utilisateur vers le routage direct. 

- [Un utilisateur sur Skype Entreprise site](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)avec Voix Entreprise, qui passe au service en ligne et utilise un plan d’appel Microsoft.  Pour migrer cet utilisateur vers Teams, vous devez déplacer le compte local de l’Skype Entreprise vers le cloud. Vous devez coordonner le déplacement avec A) le port du numéro de téléphone de cet utilisateur vers un plan d’appels Microsoft ou B) en attribuant un nouveau numéro d’abonné à partir des régions disponibles.

Cet article fournit une vue d’ensemble générale uniquement. Pour plus d’informations, voir Système téléphonique les plans [de routage et](direct-routing-landing-page.md) [d’appel directs.](calling-plan-landing-page.md) 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>À partir Skype Entreprise Online avec les forfaits d’appels Microsoft 

Ce scénario est le scénario de mise à niveau le plus simple impliquant voix. 

1. Assurez-vous qu’une licence de licence Teams a été affectée aux utilisateurs. Par défaut, lorsque vous affectez une licence Microsoft 365 ou Office 365 licence, Teams est activé. À moins que vous n’activiez précédemment Teams licence de licence, aucune action ne devrait être nécessaire.

2.  Si les utilisateurs ont déjà un plan d’appel Microsoft avec un numéro de téléphone, la seule modification requise est d’affecter le mode TeamsOnly de l’utilisateur dans TeamsUpgradePolicy. Avant d’affecter le mode TeamsOnly, les appels PSTN entrants arriveront dans le client Skype Entreprise utilisateur. Après la mise à niveau vers le mode TeamsOnly, les appels PSTN entrants arriveront dans le client Teams utilisateur.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>À partir Skype Entreprise Online avec voix sur site

Dans ce scénario, l’utilisateur est déjà dans Skype Entreprise Online. La connectivité PSTN de l’utilisateur est en local, soit en utilisant Skype Entreprise Server mode hybride, soit la version Cloud Connector. Pour migrer ces utilisateurs vers le mode TeamsOnly avec la fonctionnalité PSTN, vous devez leur permettre d’utiliser le routage direct. Avec le routage direct, les ligne PSTN se connectent directement au service de routage direct via votre contrôleur de session en bordure (SBC) local.

Les étapes de base sont répertoriées ci-dessous.  Les étapes 1 à 4 sont répertoriées dans la séquence suggérée, mais elles peuvent être réalisées dans n’importe quel ordre. Ces étapes doivent être accomplies avant l’étape 5.

1. Si vous affectez la stratégie à l’échelle du client à l’un des modes Skype Entreprise, assurez-vous d’utiliser le mode Îles en lui attribuant explicitement le mode Îles, comme décrit précédemment.

2. Configurez votre client pour le routage direct. Voir [le résumé de la configuration par client du routage direct.](#summary-of-per-tenant-configuration-of-direct-routing)

3. Si vous le souhaitez, configurez différentes stratégies Teams de ces utilisateurs (par exemple, TeamsMesspolicy, TeamsMeetingPolicy, et ainsi de suite). Vous pouvez configurer des poicies à tout moment. Toutefois, si vous voulez vous assurer que les utilisateurs ont la configuration correcte lors de la mise à niveau, configurez ces stratégies avant que l’utilisateur ne passe en mode TeamsOnly.

4. Préparer les utilisateurs sélectionnés pour la migration vocale : 
   - Si nécessaire, attribuez la licence Teams licence.  En supposant que l’utilisateur est déjà fonctionnel dans Skype Entreprise Online voix sur site, l’utilisateur dispose déjà d’Skype Entreprise Plan 2 et Téléphone Microsoft Système. Laissez ces deux plans activés, y compris la licence Skype Entreprise Online Plan 2.  
   - Affectez le site OnlineVoiceRoutingPolicy souhaité. 

5. Mettre à niveau l’utilisateur : ces étapes doivent être coordonnées. 

   - Dans Microsoft 365 ou Office 365, mettre à niveau l’utilisateur en mode TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - Sur le SBC, configurez le routage vocal pour activer les appels entrants en envoyant des appels vers le routage direct plutôt que vers le serveur de médiation local.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>Du Skype Entreprise Server local, avec l’Voix Entreprise, au routage direct

Dans ce scénario, l’utilisateur est toujours Skype Entreprise sur site. La connectivité PSTN de l’utilisateur est également sur site. Pour migrer cet utilisateur vers le mode TeamsOnly avec la fonctionnalité PSTN, vous devez activer le routage direct de l’utilisateur, puis le déplacer vers le cloud. 
 
Les étapes de base sont répertoriées ci-dessous. Les étapes 1 à 5 sont répertoriées dans la séquence suggérée, mais elles peuvent être réalisées dans n’importe quel ordre. Vous devez effectuer les étapes 1 à 5 avant l’étape 6.

1. Si vous allez définir la stratégie à l’échelle du client sur l’un des modes Skype Entreprise, assurez-vous d’utiliser le mode Îles existant en lui attribuant explicitement le mode Îles, comme décrit précédemment.

2. Si vous ne l’avez pas déjà fait, configurez l’organisation pour [un Skype Entreprise hybride.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

3. Configurez votre client pour le routage direct. Voir [le résumé de la configuration par client du routage direct.](#summary-of-per-tenant-configuration-of-direct-routing)

4. Si vous le souhaitez, configurez différentes stratégies Teams utilisateurs (par exemple, TeamsMess paysPolicy, TeamsMeetingPolicy). Vous pouvez configurer des stratégies à tout moment. Toutefois, si vous voulez vous assurer que les utilisateurs ont la configuration correcte lors de la mise à niveau, configurez ces stratégies avant que l’utilisateur ne soit mis à niveau vers TeamsOnly.

5. Attribuez les Microsoft 365 licences Office 365 licences d’utilisation, si nécessaire.  L’utilisateur doit avoir à la fois Teams et Skype Entreprise Online Plan 2 et Système téléphonique. Si le Skype Entreprise Online Plan 2 est désactivé, réactivez-le.  

6. Mettre à niveau l’utilisateur : ces étapes doivent être coordonnées. 

   - À l’aide des outils Skype Entreprise locaux, exécutez-Move-CsUser avec -MoveToTeams switch. Si vous utilisez une version de Skype Entreprise Server qui ne prend pas en charge le commutateur -MoveToTeams, exécutez d’abord Move-CsUser, puis affectez le mode TeamsOnly dans une console d’administration PowerShell distante ou Teams client.

   - Sur le SBC, configurez le routage vocal pour activer les appels entrants en envoyant des appels vers le routage direct plutôt que vers le serveur de médiation local. 

   - Dans Microsoft 365 ou Office 365 : Affectez onlineVoiceRoutingPolicy pour activer les appels sortants. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>De Skype Entreprise Server l’offre en local, avec Voix Entreprise, à Microsoft Calling Plan

Dans ce scénario, l’utilisateur est toujours Skype Entreprise sur site. La connectivité PSTN de l’utilisateur est également sur site. Pour migrer cet utilisateur vers le mode TeamsOnly avec la fonctionnalité PSTN, vous devez déplacer l’utilisateur vers le cloud et le faire migrer de l’ancien opérateur vers un plan d’appel Microsoft, ou lui attribuer un nouveau numéro. 

Les étapes de base sont répertoriées ci-dessous.Les étapes 1 à 5 sont répertoriées dans la séquence suggérée, mais elles peuvent être réalisées dans n’importe quel ordre. Vous devez effectuer les étapes 1 à 5 avant l’étape 6. 

1. Si vous allez définir la stratégie à l’échelle du client sur l’un des modes Skype Entreprise, assurez-vous d’utiliser le mode Îles existant en lui attribuant explicitement le mode Îles, comme décrit précédemment. 

2. Si vous ne l’avez pas déjà fait, configurez l’organisation pour [un Skype Entreprise hybride.](/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

3. Si vous le souhaitez, configurez différentes stratégies Teams de ces utilisateurs (par exemple, TeamsMesspolicy, TeamsMeetingPolicy, et ainsi de suite). Vous pouvez configurer des stratégies à tout moment. Toutefois, si vous voulez vous assurer que les utilisateurs ont la configuration correcte lors de la mise à niveau, configurez ces stratégies avant que l’utilisateur ne soit mis à niveau vers TeamsOnly. 

4. Attribuez les Microsoft 365 licences Office 365 licences d’utilisation, si nécessaire.L’utilisateur doit avoir à la fois Teams et Skype Entreprise Online Plan 2 et Système téléphonique. Si le Skype Entreprise Online Plan 2 est désactivé, réactivez-le.  

5. Obtenez des numéros de téléphone pour vos utilisateurs. (Pour plus d’informations, [voir Gérer les numéros de téléphone pour votre organisation.)](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

   - Si vous comptez réutiliser les numéros, envoyez une demande de portage à votre opérateur.  
   - Vous pouvez également acheter de nouveaux numéros directement auprès de Microsoft. 

6. Mettre à niveau l’utilisateur et, si nécessaire, affecter LineUri. À l’aide des outils Skype Entreprise locaux, exécutez-Move-CsUser avec le commutateur -MoveToTeams.  

    - Si vous portez des numéros vers Microsoft, vous devez coordonner le minutage de cette opération lorsque le port se produit. 

    - Si vous utilisez de nouveaux numéros de Microsoft, vous devrez modifier l’uri LineUri de l’utilisateur une fois l’utilisateur déplacé en ligne à l’aide de Set-CsPhoneNumberAssignment.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Résumé de la configuration par client du routage direct 

1. Assurez-vous que votre contrôleur de session border Controller (SBC) est pris en charge avec le routage direct en [](direct-routing-border-controllers.md)l’examiner. Assurez-vous également que vous avez la bonne version du microprogramme.  

2. Associez votre SBC local au service Teams routage direct. Pour plus d’informations, [voir Associer le SBC au service de routage direct d’Système téléphonique.](direct-routing-configure.md) 

3. Cette configuration est essentiellement un miroir de la configuration en local. La configuration en ligne est composée des : 
   - OnlineVoiceRoutingPolicy (basé sur VoiceRoutingPolicy sur site si la migration d’utilisateurs à partir de Skype Entreprise Online et sur VoicePolicy si la migration d’utilisateurs à partir du site avec Voix Entreprise).
   - Objets OnlinePSTNUsage (selon l’utilisation PSTN en local). 
   - Objets OnlineVoiceRoute (sur la base de VoiceRoute local). 

Pour plus d’informations, [voir Configurer le routage direct.](direct-routing-configure.md) 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Gérer la propriété EnterpriseVoiceEnabled lors de la migration 

Que ce soit à l’aide du routage direct ou d’un plan d’appel Microsoft, un utilisateur doit avoir EnterpriseVoiceEnabled=true dans Azure AD pour que l’utilisateur utilise les fonctionnalités PSTN.  EnterpriseVoiceEnabled (« Ev-enabled ») est une propriété (et non une stratégie) qui existe à la fois dans un annuaire local et dans le cloud. La valeur dans le cloud est importante pour Teams.  La logique exacte de la façon dont ev-enabled est définie sur true dépend du scénario suivant : 

- Si l’utilisateur est activé sur EV sur un site Skype Entreprise Server et qu’une licence Système téléphonique lui est attribuée avant de le déplacer vers le cloud avec Move-CsUser, l’utilisateur en ligne est fourni avec EV-enabled=true. 

- Si une licence teamsOnly ou Skype Entreprise Online existante se voit attribuer une licence Système téléphonique, la valeur activé pour EV n’est pas définie sur true par défaut. C’est également le cas si un utilisateur sur site est déplacé vers le cloud avant d’affecter la Système téléphonique utilisateur. Dans les deux cas, l’administrateur doit spécifier l’cmdlet suivante : 

  ```PowerShell
  Set-CsPhoneNumberAssignment -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Liens connexes

[Planifier votre solution Teams voix](cloud-voice-landing-page.md)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer la connectivité hybride entre les Skype Entreprise Server et les Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utilisation du service Meeting Migration Service (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
