---
title: Considérations en rapport avec la mise à niveau vers Teams à partir d’un déploiement local de Skype Entreprise
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Considérations en rapport avec la voix pour la mise à niveau de Skype Entreprise vers Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8a9783f5d60e5a595d548bbfc83ee013500934ed
ms.sourcegitcommit: b816ae9de91f3d01e795a69a00465a70003069b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/16/2020
ms.locfileid: "49686430"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>Considérations en rapport avec le réseau PSTN pour la mise à niveau vers Teams à partir de Skype Entreprise en local

Cet article décrit les considérations concernant le réseau téléphonique commuté (PSTN) lors de la mise à niveau vers Teams.   


Par ailleurs, les articles suivants décrivent les concepts de mise à niveau et les comportements de coexistence importants :

- [Coexistence de Teams et de Skype Entreprise](upgrade-to-teams-on-prem-coexistence.md)
- [Modes de coexistence - Référence](migration-interop-guidance-for-teams-with-skype.md)
- [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - L’utilisation du système téléphonique avec Teams n’est prise en charge que lorsque l’utilisateur est en mode TeamsOnly.  Si l’utilisateur est en mode Îles, Phone System n’est pris en charge qu’avec Skype Entreprise. 
 > - Les paramètres de forwardage, d’appel d’équipe et de délégation de Skype Entreprise ne sont pas migrés et doivent être recréés pour Teams.
 > - Pour obtenir une vue d’ensemble des fonctionnalités vocales cloud de Microsoft Teams et aider à déterminer la solution vocale Microsoft appropriée pour votre organisation, consultez Planifier votre [solution vocale Teams.](cloud-voice-landing-page.md)


## <a name="pstn-calling-scenarios"></a>Scénarios d’appel PSTN

Il existe quatre scénarios d’appel possibles lors du passage en mode TeamsOnly :

- [Un utilisateur dans Skype Entreprise Online, avec un plan d’appel Microsoft.](#from-skype-for-business-online-with-microsoft-calling-plans) Lors de la mise à niveau, cet utilisateur continuera à avoir une offre Microsoft Calling.

- [Un utilisateur dans Skype Entreprise Online,](#from-skype-for-business-online-with-on-premises-voice) avec des fonctionnalités vocales en local par le biais de Skype Entreprise en local ou dans la version Cloud Connector. La mise à niveau de l’utilisateur vers Teams doit être coordonnée avec la migration de l’utilisateur vers le routage direct pour s’assurer que l’utilisateur TeamsOnly dispose de la fonctionnalité PSTN.

- [Un utilisateur de Skype](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)Entreprise sur site avec Voix Entreprise, qui passe à la connexion en ligne et maintient la connectivité RSTN sur site.  La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud et la coordination de ce déplacement avec la migration de l’utilisateur vers le routage direct. 

- [Un utilisateur de Skype Entreprise sur](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)site avec Voix Entreprise, qui passe au service en ligne et utilise un plan d’appel Microsoft.  La migration de cet utilisateur vers Teams nécessite le déplacement du compte Skype Entreprise local de l’utilisateur vers le cloud et la coordination du déplacement avec l’un des A) port du numéro de téléphone de cet utilisateur vers un plan d’appels Microsoft ou B) et l’affectation d’un nouveau numéro d’abonné à partir des régions disponibles.

Cet article fournit une vue d’ensemble générale uniquement. Pour plus d’informations, consultez les plans [de routage et](direct-routing-landing-page.md) d’appel [directs du système téléphonique.](calling-plan-landing-page.md) 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>À partir de Skype Entreprise Online avec les forfaits d’appels Microsoft 

Il s’agit du scénario de mise à niveau le plus simple impliquant voice. 

1. Assurez-vous qu’une licence Teams a été attribuée aux utilisateurs. Par défaut, lorsque vous affectez une licence Microsoft 365 ou Office 365, Teams est activé, donc, sauf si vous avez précédemment désactivé la licence Teams, aucune action ne doit être nécessaire.

2.  Si les utilisateurs ont déjà un plan d’appel Microsoft avec un numéro de téléphone, la seule modification requise est d’affecter le mode TeamsOnly de l’utilisateur dans TeamsUpgradePolicy.  Avant d’affecter le mode TeamsOnly, les appels PSTN entrants arriveront dans le client Skype Entreprise de l’utilisateur. Après la mise à niveau vers le mode TeamsOnly, les appels PSTN entrants arriveront dans le client Teams de l’utilisateur.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>À partir de Skype Entreprise Online avec voix sur site

Dans ce scénario, l’utilisateur se trouve déjà dans Skype Entreprise Online, mais sa connectivité PSTN est sur site, soit en utilisant Skype Entreprise Server en mode hybride, soit la version Cloud Connector. La migration de ces utilisateurs vers le mode TeamsOnly avec la fonctionnalité PSTN signifie leur activation pour un routage direct, dans lequel des ligne PSTN se connectent directement au service de routage direct dans le cloud, via votre contrôleur de session en bordure (SBC) local.

Les étapes de base sont répertoriées ci-dessous.  Les étapes 1 à 4 sont répertoriées dans la séquence suggérée, mais elles peuvent être réalisées dans n’importe quel ordre. L’essentiel est que toutes ces étapes soient accomplies avant l’étape 5.

1. Si vous affectez la stratégie à l’échelle du client à l’un des modes Skype Entreprise, veillez à affecter explicitement ce mode à tous les utilisateurs des îles, comme décrit précédemment.

2. Configurez votre client pour le routage direct. Voir [le résumé de la configuration par client du routage direct.](#summary-of-per-tenant-configuration-of-direct-routing)

3. Si vous le souhaitez, configurez différentes stratégies Teams pour ces utilisateurs (par exemple, TeamsMesspolicy, TeamsMeetingPolicy, etc.). Cette configuration peut être effectuée à tout moment, mais si vous voulez vous assurer que les utilisateurs ont la configuration correcte lors de la mise à niveau, il est préférable de le faire avant que l’utilisateur soit mis à niveau en mode TeamsOnly.

4. Préparer les utilisateurs sélectionnés pour la migration vocale : 
   - Si nécessaire, attribuez la licence Teams.  En supposant que l’utilisateur dispose déjà des fonctions vocales dans Skype Entreprise Online sur site, l’utilisateur dispose déjà de Skype Entreprise Plan 2 et de Microsoft Phone System. Laissez ces deux plans activés, y compris la licence Skype Entreprise Online (plan 2).  
   - Affectez le site OnlineVoiceRoutingPolicy souhaité. 

5. Mettre à niveau l’utilisateur : ces étapes doivent être coordonnées. 

   - Dans Microsoft 365 ou Office 365, mettre à niveau l’utilisateur en mode TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - Sur le SBC, configurez le routage vocal pour activer les appels entrants en envoyant des appels vers le routage direct plutôt que vers le serveur de médiation local.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>À partir de Skype Entreprise Server local, avec Voix Entreprise, vers un routage direct

Dans ce scénario, l’utilisateur est toujours homed dans Skype Entreprise sur site, et sa connectivité PSTN est également sur site. La migration de ces utilisateurs vers le mode TeamsOnly avec la fonctionnalité PSTN implique de les activer pour un routage direct, puis de déplacer l’utilisateur vers le cloud. 
 
Les étapes de base sont répertoriées ci-dessous.  Les étapes 1 à 5 sont répertoriées dans la séquence suggérée, mais elles peuvent être réalisées dans n’importe quel ordre. L’essentiel est que toutes ces étapes soient accomplies avant l’étape 6.

1. Si vous allez définir la stratégie à l’échelle du client sur l’un des modes Skype Entreprise, assurez-vous d’utiliser le mode Îles existant en lui attribuant explicitement le mode Îles, comme décrit précédemment.

2. Si vous ne l’avez pas déjà fait, [configurez l’organisation pour Skype Entreprise hybride.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

3. Configurez votre client pour le routage direct. Voir [le résumé de la configuration par client du routage direct.](#summary-of-per-tenant-configuration-of-direct-routing)

4. Si vous le souhaitez, configurez différentes stratégies Teams pour ces utilisateurs (par exemple, TeamsMesspolicy, TeamsMeetingPolicy, etc.). Cette configuration peut être effectuée à tout moment, mais si vous voulez vous assurer que les utilisateurs ont la configuration correcte lors de la mise à niveau, il est préférable de le faire avant que l’utilisateur soit mis à niveau vers TeamsOnly.

5. Attribuez les licences Microsoft 365 ou Office 365 si nécessaire.  L’utilisateur doit avoir Teams et Skype Entreprise Online (plan 2), ainsi que Phone System. Si Skype Entreprise Online (plan 2) est désactivé, réactivez-le.  

6. Mettre à niveau l’utilisateur : ces étapes doivent être coordonnées. 

   - À l’aide des outils skype entreprise locaux, exécutez-Move-CsUser avec -MoveToTeams switch. Si vous utilisez une version de Skype Entreprise Server qui ne prend pas en charge le commutateur -MoveToTeams, exécutez tout d’abord Move-CsUser puis affectez le mode TeamsOnly dans le client distant PowerShell ou la Console d’administration Teams.

   - Sur le SBC, configurez le routage vocal pour activer les appels entrants en envoyant des appels vers le routage direct plutôt que vers le serveur de médiation local. 

   - Dans Microsoft 365 ou Office 365 : affectez le service OnlineVoiceRoutingPolicy approprié pour activer les appels sortants. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>De Skype Entreprise Server local, avec Voix Entreprise, au plan d’appel Microsoft

Dans ce scénario, l’utilisateur est toujours homed dans Skype Entreprise sur site, et sa connectivité PSTN est également sur site. La migration de ces utilisateurs vers le mode TeamsOnly avec la fonctionnalité PSTN signifie le déplacement de l’utilisateur vers le cloud et le portage de son numéro à partir de l’ancien opérateur vers un plan d’appels Microsoft ou l’attribution d’un nouveau numéro à l’utilisateur. 

Les étapes de base sont répertoriées ci-dessous.Les étapes 1 à 5 sont répertoriées dans la séquence suggérée, mais elles peuvent être réalisées dans n’importe quel ordre. L’essentiel est que toutes ces étapes soient accomplies avant l’étape 6. 

1. Si vous allez définir la stratégie à l’échelle du client sur l’un des modes Skype Entreprise, assurez-vous d’utiliser le mode Îles existant en lui attribuant explicitement le mode Îles, comme décrit précédemment. 

2. Si vous ne l’avez pas déjà fait, [configurez l’organisation pour Skype Entreprise hybride.](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity) 

3. Si vous le souhaitez, configurez différentes stratégies Teams pour ces utilisateurs (par exemple, TeamsMesspolicy, TeamsMeetingPolicy, etc.). Cette configuration peut être effectuée à tout moment, mais si vous voulez vous assurer que les utilisateurs ont la configuration correcte lors de la mise à niveau, il est préférable de le faire avant que l’utilisateur soit mis à niveau vers TeamsOnly. 

4. Attribuez les licences Microsoft 365 ou Office 365 si nécessaire.L’utilisateur doit avoir Teams et Skype Entreprise Online (plan 2), ainsi que Phone System. Si Skype Entreprise Online (plan 2) est désactivé, réactivez-le.  

5. Obtenez des numéros de téléphone pour vos utilisateurs. (Pour plus d’informations, [voir Gérer les numéros de téléphone pour votre organisation.)](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization)

   - Si vous comptez utiliser de nouveau les numéros, envoyez une demande de portage à votre opérateur.  
   - Vous pouvez également acheter de nouveaux numéros directement auprès de Microsoft. 

6. Mettre à niveau l’utilisateur et, si nécessaire, affecter LineUri. À l’aide des outils Skype Entreprise locaux, exécutez-Move-CsUser avec le commutateur -MoveToTeams.  

    - Si vous portez des numéros vers Microsoft, vous devez coordonner le minutage de cette opération lorsque le port se produit. 

    - Si vous utilisez de nouveaux numéros de Microsoft, vous devez modifier l’uri LineUri de l’utilisateur. Cette mise à jour doit être effectuée une fois l’utilisateur déplacé en ligne à l’aide de Set-CsOnlineVoiceUser.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Résumé de la configuration par client du routage direct 

1. Assurez-vous que votre contrôleur de session border Controller (SBC) est pris en charge avec le routage direct en [](direct-routing-border-controllers.md)l’examiner. Vous devez également vérifier que vous avez la bonne version du microprogramme.  

2. Associez votre SBC local au service de routage direct Teams. Pour plus d’informations, [voir Associer le SBC au service de routage direct du système téléphonique.](direct-routing-configure.md) 

3. Cette configuration est essentiellement un miroir de la configuration en local. La configuration en ligne est composée des : 
   - OnlineVoiceRoutingPolicy (basé sur VoiceRoutingPolicy sur site si la migration d’utilisateurs à partir de Skype Entreprise Online, et sur VoicePolicy si la migration d’utilisateurs à partir du site avec Voix Entreprise).
   - Objets OnlinePSTNUsage (selon l’utilisation PSTN en local). 
   - Objets OnlineVoiceRoute (sur la base de VoiceRoute local). 

Pour plus d’informations, [voir Configurer le routage direct.](direct-routing-configure.md) 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Gérer la propriété EnterpriseVoiceEnabled lors de la migration 

Que ce soit à l’aide du routage direct ou d’un plan d’appel Microsoft, un utilisateur doit avoir EnterpriseVoiceEnabled=true dans Azure AD pour que l’utilisateur utilise les fonctionnalités PSTN.  EnterpriseVoiceEnabled (« Ev-enabled ») est une propriété (et non une stratégie) qui existe à la fois dans un annuaire local et dans le cloud. La valeur du cloud est importante pour Teams.  La logique exacte de la façon dont ev-enabled est définie sur true dépend du scénario suivant : 

- Si l’utilisateur est activé sur Skype Entreprise Server sur site et qu’une licence Système téléphonique est attribuée à l’utilisateur avant de le déplacer vers le cloud avec Move-CsUser, l’utilisateur en ligne est fourni avec EV-enabled=true. 

- Si une licence Système téléphonique est affectée à un utilisateur teamsOnly ou Skype Entreprise Online existant, la valeur de la licence EV n’est pas définie par défaut sur True.  C’est également le cas si un utilisateur sur site est déplacé vers le cloud avant d’affecter la licence Phone System. Dans les deux cas, l’administrateur doit spécifier l’cmdlet suivante : 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Liens connexes

[Planifier votre solution vocale Teams](cloud-voice-landing-page.md)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utilisation du service Meeting Migration Service (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

