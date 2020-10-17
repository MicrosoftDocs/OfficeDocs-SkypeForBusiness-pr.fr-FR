---
title: Effectuer une mise à niveau vers teams à partir d’un déploiement local de Skype entreprise-Microsoft teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/16/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Mise à niveau de Skype entreprise vers considérations relatives à la voix dans teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6b27694c476fc1ab571716939ad57cc3f2dae20e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533551"
---
# <a name="pstn-considerations-when-upgrading-to-teams-mdash-for-it-administrators"></a>Considérations RTC lors de la mise à niveau vers teams &mdash; pour les administrateurs informatiques

Cet article décrit les aspects du réseau téléphonique public commuté (RTC) lors de la mise à niveau vers Teams. Cet article est le sixième d’entre eux qui décrivent des concepts et une implémentation de mise à niveau pour les administrateurs informatiques.  

- [Vue d’ensemble](upgrade-to-teams-on-prem-overview.md)
- [Méthodes de mise à niveau](upgrade-to-teams-on-prem-upgrade-methods.md)
- [Outils de gestion de votre mise à niveau](upgrade-to-teams-on-prem-tools.md)
- [Autres considérations concernant les organisations avec Skype entreprise en local](upgrade-to-teams-on-prem-considerations.md)
- [Implémenter votre mise à niveau](upgrade-to-teams-on-prem-implement.md)
- **Considérations relatives au réseau téléphonique commuté (PSTN)** (cet article)

De plus, les articles suivants décrivent des concepts importants de mise à niveau et des comportements de coexistence :

- [Coexistence des équipes et de Skype entreprise](upgrade-to-teams-on-prem-coexistence.md)
- [Modes de coexistence-référence](migration-interop-guidance-for-teams-with-skype.md)
- [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)


 > [!NOTE]
 > - L’utilisation du système téléphonique avec teams est uniquement prise en charge lorsque l’utilisateur est en mode TeamsOnly.  Si l’utilisateur est en mode îlot, le système téléphonique est uniquement pris en charge par Skype entreprise. 
 > - Les paramètres de transfert d’appel et de délégation de Skype entreprise ne sont pas migrés et devront être recréés pour Teams.


## <a name="pstn-calling-scenarios"></a>Scénarios d’appel RTC

Il existe quatre scénarios d’appel possibles lors du passage au mode TeamsOnly :

- [Un utilisateur de Skype entreprise Online avec un plan d’appels Microsoft](#from-skype-for-business-online-with-microsoft-calling-plans). Suite à la mise à niveau, cet utilisateur aura besoin d’un plan d’appels Microsoft.

- [Un utilisateur de Skype entreprise Online avec la fonction vocale locale](#from-skype-for-business-online-with-on-premises-voice) via Skype entreprise local ou la version Cloud Connector. La mise à niveau de l’utilisateur vers teams doit être coordonnée avec la migration de l’utilisateur pour diriger le routage afin de garantir que l’utilisateur TeamsOnly dispose de la fonctionnalité RTC.

- [Un utilisateur de Skype entreprise sur site avec voix entreprise](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), qui va basculer vers une connectivité RTC sur site.  La migration de cet utilisateur vers teams nécessite le passage du compte Skype entreprise local de l’utilisateur dans le Cloud, et le coordination du déplacement avec la migration de celui-ci pour le routage directe. 

- [Un utilisateur de Skype entreprise sur site avec voix entreprise](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), qui sera déplacé vers en ligne et utilisant un forfait d’appel Microsoft.  La migration de cet utilisateur vers teams nécessite le passage du compte Skype entreprise local de l’utilisateur dans le Cloud, et la coordination de la migration à l’aide de l’un des numéros de téléphone de l’utilisateur vers un forfait d’appel Microsoft ou B), en attribuant un nouveau numéro d’abonné à partir des régions disponibles.

Cet article fournit une vue d’ensemble de haut niveau. Pour plus d’informations, reportez-vous à la section routage et [appels](calling-plan-landing-page.md) [directs du système téléphonique](direct-routing-landing-page.md) . 

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>À partir de Skype entreprise Online avec les offres d’appel Microsoft 

Il s’agit du scénario de mise à niveau le plus simple avec la voix. 

1. Vérifiez que les utilisateurs ont reçu une licence d’équipe. Par défaut, lorsque vous attribuez une licence Microsoft 365 ou Office 365, teams est activé, donc sauf si vous avez précédemment désactivé la licence Teams, aucune action n’est nécessaire.

2.  Si les utilisateurs ont déjà une offre d’appels Microsoft avec un numéro de téléphone, la seule modification obligatoire consiste à affecter le mode TeamsOnly de l’utilisateur dans TeamsUpgradePolicy.  Avant d’affecter le mode TeamsOnly, les appels RTC entrants apparaissent sur le client Skype entreprise de l’utilisateur. Après la mise à niveau vers le mode TeamsOnly, les appels RTC entrants s’afficheront dans le client teams de l’utilisateur.  

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>À partir de Skype entreprise Online avec la voix locale

Dans ce scénario, l’utilisateur se trouve déjà dans Skype entreprise Online, mais sa connectivité PSTN est locale, soit avec Skype entreprise Server en mode hybride, soit dans la version Cloud Connector. La migration de ces utilisateurs vers le mode TeamsOnly avec la fonctionnalité RTC implique de les activer pour le routage direct, dans lesquels les Trunks RTC se connectent directement au service de routage direct dans le Cloud, via votre contrôleur de bordure de session (SBC) local.

Les étapes de base sont décrites ci-dessous.  Les étapes 1-4 sont répertoriées dans la séquence proposée, mais peuvent être effectuées dans n’importe quel ordre. La clé consiste à ce que toutes ces instructions soient achevées avant l’étape 5.

1. Si vous définissez la stratégie à l’échelle du client sur l’un des modes Skype entreprise, veillez à ce que tous les utilisateurs d’îlot existants en leur attribuant explicitement le mode d’attribution, comme décrit précédemment.

2. Configurer votre client pour le routage direct. Voir [Résumé de la configuration par client du routage direct](#summary-of-per-tenant-configuration-of-direct-routing).

3. Si vous le souhaitez, configurez différentes stratégies d’équipes pour ces utilisateurs (par exemple, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Vous pouvez effectuer cette opération à tout moment, mais si vous voulez vous assurer que les utilisateurs disposent de la configuration correcte lors de la mise à niveau, nous vous conseillons de le faire avant de procéder à la mise à niveau vers le mode TeamsOnly.

4. Préparer la migration de certains utilisateurs pour la boîte vocale : 
   - Le cas échéant, attribuez la licence Teams.  En supposant que l’utilisateur est déjà opérationnel dans Skype entreprise Online, l’utilisateur dispose déjà de Skype entreprise plan 2 ainsi que du système Microsoft Phone. Laissez ces offres activées, y compris la licence de plan 2 de Skype entreprise online.  
   - Assignez la OnlineVoiceRoutingPolicy souhaitée. 

5. Mise à niveau de l’utilisateur : les étapes suivantes doivent être coordonnées. 

   - Dans Microsoft 365 ou Office 365, procédez à une mise à niveau de l’utilisateur en mode TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - Sur la SBC, configurez le routage de la voix pour permettre les appels entrants en envoyant des appels vers le routage direct plutôt que vers le serveur de médiation local.


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>De Skype entreprise Server en local, avec Enterprise Voice, pour le routage direct

Dans ce scénario, l’utilisateur est toujours hébergé sur site dans Skype entreprise et sa connectivité PSTN est également locale. La migration de ces utilisateurs vers le mode TeamsOnly avec la fonctionnalité RTC implique de les activer pour le routage direct, puis de déplacer l’utilisateur vers le Cloud. 
 
Les étapes de base sont décrites ci-dessous.  Les étapes 1-5 sont répertoriées dans la séquence proposée, mais peuvent être effectuées dans n’importe quel ordre. La clé consiste à ce que toutes ces instructions soient exécutées avant l’étape 6.

1. Si vous définissez la stratégie à l’échelle du client sur l’un des modes Skype entreprise, veillez à ce que les utilisateurs de l’îlot actuel en attribuant explicitement le mode d’îlot, comme décrit précédemment.

2. Si vous ne l’avez pas déjà fait, [configurez l’Organisation pour Skype entreprise hybride](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Configurer votre client pour le routage direct. Voir [Résumé de la configuration par client du routage direct](#summary-of-per-tenant-configuration-of-direct-routing).

4. Si vous le souhaitez, configurez différentes politiques d’équipe pour ces utilisateurs (par exemple, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Vous pouvez effectuer cette opération à tout moment, mais si vous voulez vous assurer que les utilisateurs disposent de la configuration correcte lors de la mise à niveau, nous vous conseillons de le faire avant de procéder à la mise à niveau vers TeamsOnly.

5. Attribuez les licences Microsoft 365 ou Office 365 le cas échéant.  L’utilisateur doit disposer des équipes et de Skype entreprise Online plan 2, ainsi que du système téléphonique. Si le plan 2 de Skype entreprise Online est désactivé, réactivez-le.  

6. Mise à niveau de l’utilisateur : les étapes suivantes doivent être coordonnées. 

   - À l’aide des outils Skype entreprise locaux, exécutez Move-CsUser avec le commutateur-MoveToTeams. Si vous utilisez une version de Skype entreprise Server qui ne prend pas en charge le commutateur-MoveToTeams, vous devez d’abord exécuter Move-CsUser puis affecter le mode TeamsOnly dans la console d’administration distante du client.

   - Sur la SBC, configurez le routage de la voix pour permettre les appels entrants en envoyant des appels vers le routage direct plutôt que vers le serveur de médiation local. 

   - Dans Microsoft 365 ou Office 365 : attribuez le OnlineVoiceRoutingPolicy approprié pour autoriser les appels sortants. 


## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>De Skype entreprise Server en local, avec Enterprise Voice, à l’offre d’appels Microsoft

Dans ce scénario, l’utilisateur est toujours hébergé sur site dans Skype entreprise et sa connectivité PSTN est également locale. La migration de ces utilisateurs vers le mode TeamsOnly avec la fonctionnalité RTC implique le déplacement de l’utilisateur dans le Cloud, en transférant son numéro entre l’ancien opérateur et un plan d’appel Microsoft ou en attribuant un nouveau numéro à l’utilisateur. 

Les étapes de base sont décrites ci-dessous.Les étapes 1-5 sont répertoriées dans la séquence proposée, mais peuvent être effectuées dans n’importe quel ordre. La clé consiste à ce que toutes ces instructions soient exécutées avant l’étape 6. 

1. Si vous définissez la stratégie à l’échelle du client sur l’un des modes Skype entreprise, veillez à ce que les utilisateurs de l’îlot actuel en attribuant explicitement le mode d’îlot, comme décrit précédemment. 

2. Si vous ne l’avez pas déjà fait, [configurez l’Organisation pour Skype entreprise hybride](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity). 

3. Si vous le souhaitez, configurez différentes stratégies d’équipes pour ces utilisateurs (par exemple, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Vous pouvez effectuer cette opération à tout moment, mais si vous voulez vous assurer que les utilisateurs disposent de la configuration correcte lors de la mise à niveau, nous vous conseillons de le faire avant de procéder à la mise à niveau vers TeamsOnly. 

4. Attribuez les licences Microsoft 365 ou Office 365 le cas échéant.L’utilisateur doit disposer des équipes et de Skype entreprise Online plan 2, ainsi que du système téléphonique. Si le plan 2 de Skype entreprise Online est désactivé, réactivez-le.  

5. Obtenez des numéros de téléphone pour vos utilisateurs. (Pour plus d’informations, voir [gérer les numéros de téléphone pour votre organisation](https://docs.microsoft.com/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization).)

   - Si vous voulez réutiliser les numéros, envoyez une demande de portage à votre opérateur.  
   - Vous pouvez aussi acheter de nouveaux numéros directement auprès de Microsoft. 

6. Mettez à jour l’utilisateur et, si nécessaire, attribuez LineUri. À l’aide des outils Skype entreprise locaux, exécutez Move-CsUser avec le commutateur-MoveToTeams.  

    - Si vous transférez des numéros vers Microsoft, vous devez coordonner le minutage de cette opération pour qu’il se produise lorsque le port intervient. 

    - Si vous utilisez de nouveaux numéros de Microsoft, vous devez modifier le LineUri de l’utilisateur. Vous devez effectuer cette opération une fois que l’utilisateur a été déplacé en ligne à l’aide de Set-CsOnlineVoiceUser.  

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Résumé de la configuration par client du routage direct 

1. Assurez-vous que votre contrôleur de bordure de session (SBC) est compatible avec le routage direct en passant en revue [cette liste](direct-routing-border-controllers.md). Vous devez également vérifier que vous disposez de la version de microprogramme correcte.  

2. Associez votre SBC local au service de routage direct Teams. Pour plus d’informations, voir [jumeler l’SBC au service de routage direct du système téléphonique](direct-routing-configure.md). 

3. Cette configuration est essentiellement un miroir de la configuration locale. La configuration en ligne se compose des éléments suivants : 
   - OnlineVoiceRoutingPolicy (sur la base de la VoiceRoutingPolicy locale lors de la migration des utilisateurs de Skype entreprise Online et sur la base d’VoicePolicy lors de la migration des utilisateurs de Skype entreprise à l’aide de la voix entreprise).
   - Objets OnlinePSTNUsage (sur la base de l’utilisation RTC locale). 
   - Objets OnlineVoiceRoute (en fonction de VoiceRoute locale). 

Pour plus d’informations, consultez [configurer le routage direct](direct-routing-configure.md). 

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Gérer la propriété EnterpriseVoiceEnabled lors de la migration 

Qu’il s’agisse de l’utilisation d’un routage direct ou d’un plan d’appels Microsoft, un utilisateur doit avoir EnterpriseVoiceEnabled = true dans Azure AD pour que l’utilisateur dispose de la fonctionnalité RTC.  EnterpriseVoiceEnabled (« EV-Enabled ») est une propriété (pas une stratégie) qui existe dans un répertoire local et dans le Cloud. La valeur du Cloud est le sujet de l’équipe.  La logique exacte de la façon dont le mode EV est défini sur true dépend du scénario suivant : 

- Si l’utilisateur est doté du service EV dans un serveur Skype entreprise local et qu’une licence de système téléphonique est affectée à l’utilisateur avant de le déplacer vers le Cloud grâce à Move-CsUser, l’utilisateur en ligne est configuré avec EV-enabled = true. 

- Si un utilisateur TeamsOnly existant ou Skype entreprise Online dispose d’une licence de système téléphonique, le EV est activé par défaut.  C’est également le cas si un utilisateur local est déplacé vers le Cloud avant d’affecter la licence du système téléphonique. Dans les deux cas, l’administrateur doit spécifier l’applet de commande suivante : 

  ```PowerShell
  Set-CsUser -EnterpriseVoiceEnabled $True 
  ```

## <a name="related-links"></a>Liens connexes

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md) 

[Configurer une connectivité hybride entre Skype entreprise Server et Microsoft 365 ou Office 365](https://docs.microsoft.com/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy?view=skype-ps)

[Utiliser le service de migration de réunion (MMS)](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)

