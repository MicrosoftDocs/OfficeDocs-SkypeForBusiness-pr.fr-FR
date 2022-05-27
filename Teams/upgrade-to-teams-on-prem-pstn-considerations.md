---
title: Considérations relatives au RTC lors de la mise à niveau vers Teams à partir de Skype Entreprise
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: Considérations relatives à la voix pour la mise à niveau de Skype Entreprise vers Teams
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- NOCSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 130ff6164de3cae82902487f70dd6eaefb631c27
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681345"
---
# <a name="pstn-considerations-for-upgrading-to-teams-from-skype-for-business-on-premises"></a>Considérations relatives au RTC pour la mise à niveau vers Teams à partir de Skype Entreprise localement

Cet article décrit les considérations relatives au réseau téléphonique commuté (RTC) lors de la mise à niveau vers Teams.

[!INCLUDE [sfbo-retirement-skype](../Skype/Hub/includes/sfbo-retirement.md)]

Les articles suivants décrivent les concepts de mise à niveau importants et les comportements de coexistence :

- [Coexistence de Teams et de Skype Entreprise](teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [Modes de coexistence - Référence](migration-interop-guidance-for-teams-with-skype.md)
- [Expérience client Teams et conformité aux modes coexistence](teams-client-experience-and-conformance-to-coexistence-modes.md)

> [!NOTE]
>
> - L’utilisation de Système téléphonique avec Teams n’est prise en charge que lorsque le compte de l’utilisateur reçoit une stratégie de mise à niveau Teams avec Teams mode uniquement.
> - L’utilisation de Système téléphonique avec Skype Entreprise n’est prise en charge que lorsque le compte de l’utilisateur reçoit une stratégie de mise à niveau Teams avec un mode SfB.
> - Système téléphonique n’est pas pris en charge lorsque le compte de l’utilisateur reçoit une stratégie de mise à niveau Teams avec le mode Îles.
> - Les paramètres de transfert d’appel, de groupe d’appels d’équipe et de délégation de Skype Entreprise ne sont pas migrés et doivent être recréés pour Teams.
> - Pour obtenir une vue d’ensemble de Microsoft Teams fonctionnalités vocales cloud et vous aider à déterminer la solution vocale Microsoft adaptée à votre organisation, consultez [Planifier votre solution vocale Teams](cloud-voice-landing-page.md).

## <a name="pstn-calling-scenarios"></a>Scénarios d’appel RTC

Il existe quatre scénarios d’appel possibles lors du passage en mode TeamsOnly :

- [Un utilisateur dans Skype Entreprise Online, avec un plan d’appel Microsoft](#from-skype-for-business-online-with-microsoft-calling-plans). Lors de la mise à niveau, cet utilisateur continuera d’avoir un plan d’appel Microsoft.

- [Un utilisateur dans Skype Entreprise Online, avec des fonctionnalités vocales locales](#from-skype-for-business-online-with-on-premises-voice) via Skype Entreprise édition locale ou Cloud Connector. Pour vous assurer que l’utilisateur TeamsOnly dispose de fonctionnalités RTC, vous devez coordonner la mise à niveau de l’utilisateur vers Teams avec la migration de l’utilisateur vers le routage direct.

- [Un utilisateur dans Skype Entreprise local avec Voix Entreprise](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing), qui passera en ligne et conservera la connectivité RTC locale.  Pour migrer cet utilisateur vers Teams, vous devez déplacer le compte Skype Entreprise local de l’utilisateur vers le cloud et coordonner ce déplacement avec la migration de l’utilisateur vers le routage direct.

- [Un utilisateur dans Skype Entreprise local avec Voix Entreprise](#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan), qui passera en ligne et utilisera un plan d’appel Microsoft.  Pour migrer cet utilisateur vers Teams, vous devez déplacer le compte Skype Entreprise local de l’utilisateur vers le cloud. Vous devez coordonner le déplacement avec A) le port du numéro de téléphone de cet utilisateur vers un plan d’appel Microsoft ou B) en affectant un nouveau numéro d’abonné à partir des régions disponibles.

Cet article fournit une vue d’ensemble générale uniquement. Pour plus d’informations, consultez [Système téléphonique plans de routage](direct-routing-landing-page.md) direct et [d’appel](calling-plan-landing-page.md).

## <a name="from-skype-for-business-online-with-microsoft-calling-plans"></a>À partir de Skype Entreprise Online avec les forfaits d’appels Microsoft

Ce scénario est le scénario de mise à niveau le plus simple impliquant la voix.

1. Assurez-vous que les utilisateurs ont reçu une licence Teams. Par défaut, lorsque vous attribuez une licence Microsoft 365 ou Office 365, Teams est activé. Sauf si vous avez précédemment désactivé la licence Teams, aucune action ne doit être nécessaire.

2. Si les utilisateurs disposent déjà d’un plan d’appel Microsoft avec un numéro de téléphone, la seule modification requise consiste à affecter le mode TeamsOnly utilisateur dans TeamsUpgradePolicy. Avant d’affecter le mode TeamsOnly, les appels RTC entrants arrivent dans le client Skype Entreprise de l’utilisateur. Après la mise à niveau vers le mode TeamsOnly, les appels RTC entrants arrivent dans le client Teams de l’utilisateur.

## <a name="from-skype-for-business-online-with-on-premises-voice"></a>À partir de Skype Entreprise Online avec voix locale

Dans ce scénario, l’utilisateur est déjà dans Skype Entreprise Online. La connectivité PSTN de l’utilisateur est locale, en utilisant Skype Entreprise Server en mode hybride ou Cloud Connector Edition. Pour migrer ces utilisateurs vers le mode TeamsOnly avec la fonctionnalité RTC, vous devez activer les utilisateurs pour le routage direct. Avec le routage direct, les jonctions RTC se connectent directement au service de routage direct via votre contrôleur de frontière de session (SBC) local.

Les étapes de base sont répertoriées ci-dessous.  Les étapes 1 à 4 sont répertoriées dans la séquence suggérée, mais elles peuvent être effectuées dans n’importe quel ordre. Ces étapes doivent être effectuées avant l’étape 5.

1. Si vous définissez la stratégie à l’échelle du locataire sur l’un des modes Skype Entreprise, veillez à ce que tous les utilisateurs existants des îles soient grand-père en leur attribuant explicitement le mode Îles, comme décrit précédemment.

2. Configurez votre locataire pour le routage direct. Consultez [le résumé de la configuration par locataire du routage direct](#summary-of-per-tenant-configuration-of-direct-routing).

3. Si vous le souhaitez, configurez différentes stratégies Teams pour ces utilisateurs (par exemple, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Vous pouvez configurer des entrées à tout moment. Toutefois, si vous souhaitez vous assurer que les utilisateurs disposent de la configuration appropriée lorsqu’ils sont mis à niveau, configurez ces stratégies avant que l’utilisateur soit mis à niveau vers le mode TeamsOnly.

4. Préparer certains utilisateurs pour la migration vocale :
   - Si nécessaire, affectez la licence Teams.  En supposant que l’utilisateur est déjà fonctionnel dans Skype Entreprise voix locale en ligne, l’utilisateur a déjà Skype Entreprise Plan 2 et Téléphone Microsoft System. Laissez ces deux plans activés, y compris la licence Skype Entreprise Online Plan 2.
   - Affectez la OnlineVoiceRoutingPolicy souhaitée.

5. Mettre à niveau l’utilisateur : ces étapes doivent être coordonnées.

   - Dans Microsoft 365 ou Office 365, mettez à niveau l’utilisateur en mode TeamsOnly (Grant-CsTeamsUpgradePolicy).
   - Sur le SBC, configurez le routage vocal pour activer les appels entrants en envoyant des appels au routage direct au lieu du serveur de médiation local.

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing"></a>De Skype Entreprise Server local, avec Voix Entreprise, au routage direct

Dans ce scénario, l’utilisateur est toujours hébergé dans Skype Entreprise local. La connectivité RTC de l’utilisateur est également locale. Pour migrer cet utilisateur en mode TeamsOnly avec la fonctionnalité RTC, vous devez activer l’utilisateur pour le routage direct, puis déplacer l’utilisateur vers le cloud.

Les étapes de base sont répertoriées ci-dessous. Les étapes 1 à 5 sont répertoriées dans la séquence suggérée, mais elles peuvent être effectuées dans n’importe quel ordre. Vous devez effectuer les étapes 1 à 5 avant l’étape 6.

1. Si vous définissez la stratégie à l’échelle du locataire sur l’un des modes Skype Entreprise, veillez à ce que les utilisateurs des îles existantes grand-père leur attribuent explicitement le mode Îles, comme décrit précédemment.

2. Si vous ne l’avez pas déjà fait, [configurez l’organisation pour Skype Entreprise hybride](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Configurez votre locataire pour le routage direct. Consultez [le résumé de la configuration par locataire du routage direct](#summary-of-per-tenant-configuration-of-direct-routing).

4. Si vous le souhaitez, configurez différentes stratégies Teams pour ces utilisateurs (par exemple, TeamsMessagingPolicy, TeamsMeetingPolicy). Vous pouvez configurer des stratégies à tout moment. Toutefois, si vous souhaitez vous assurer que les utilisateurs disposent de la configuration appropriée lorsqu’ils sont mis à niveau, configurez ces stratégies avant la mise à niveau de l’utilisateur vers TeamsOnly.

5. Affectez les licences Microsoft 365 ou Office 365 si nécessaire.  L’utilisateur doit avoir à la fois Teams et Skype Entreprise plan en ligne 2 et Système téléphonique. Si le Skype Entreprise plan en ligne 2 est désactivé, réactivez-le.

6. Mettre à niveau l’utilisateur : ces étapes doivent être coordonnées.

   - À l’aide des outils de Skype Entreprise locaux, exécutez Move-CsUser avec le commutateur -MoveToTeams. Si vous utilisez une version de Skype Entreprise Server qui ne prend pas en charge le commutateur -MoveToTeams, commencez par exécuter Move-CsUser, puis attribuez le mode TeamsOnly dans le client PowerShell distant ou Teams Administration Console.

   - Sur le SBC, configurez le routage vocal pour activer les appels entrants en envoyant des appels au routage direct au lieu du serveur de médiation local.

   - Dans Microsoft 365 ou Office 365 : affectez le OnlineVoiceRoutingPolicy approprié pour activer les appels sortants.

## <a name="from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan"></a>Du Skype Entreprise Server local, avec Voix Entreprise, au plan d’appel Microsoft

Dans ce scénario, l’utilisateur est toujours hébergé dans Skype Entreprise local. La connectivité RTC de l’utilisateur est également locale. Pour migrer cet utilisateur en mode TeamsOnly avec la fonctionnalité RTC, vous devez déplacer l’utilisateur vers le cloud et porter son numéro de l’ancien opérateur vers un plan d’appel Microsoft, ou lui attribuer un nouveau numéro.

Les étapes de base sont répertoriées ci-dessous. Les étapes 1 à 5 sont répertoriées dans la séquence suggérée, mais elles peuvent être effectuées dans n’importe quel ordre. Vous devez effectuer les étapes 1 à 5 avant l’étape 6.

1. Si vous définissez la stratégie à l’échelle du locataire sur l’un des modes Skype Entreprise, veillez à ce que les utilisateurs des îles existantes grand-père leur attribuent explicitement le mode Îles, comme décrit précédemment.

2. Si vous ne l’avez pas déjà fait, [configurez l’organisation pour Skype Entreprise hybride](/SkypeForBusiness/hybrid/configure-hybrid-connectivity).

3. Si vous le souhaitez, configurez différentes stratégies Teams pour ces utilisateurs (par exemple, TeamsMessagingPolicy, TeamsMeetingPolicy, etc.). Vous pouvez configurer des stratégies à tout moment. Toutefois, si vous souhaitez vous assurer que les utilisateurs disposent de la configuration appropriée lorsqu’ils sont mis à niveau, configurez ces stratégies avant la mise à niveau de l’utilisateur vers TeamsOnly.

4. Affectez les licences Microsoft 365 ou Office 365 si nécessaire. L’utilisateur doit avoir à la fois Teams et Skype Entreprise plan en ligne 2 et Système téléphonique. Si le Skype Entreprise plan en ligne 2 est désactivé, réactivez-le.

5. Obtenez les numéros de téléphone de vos utilisateurs. (Pour plus d’informations, consultez [Gérer les numéros de téléphone de votre organisation](./manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md).)

   - Si vous réutilisez les numéros, envoyez une demande de portage à votre opérateur.
   - Vous pouvez également acquérir de nouveaux numéros directement auprès de Microsoft.

6. Mettez à niveau l’utilisateur et, si nécessaire, affectez LineUri. À l’aide des outils de Skype Entreprise locaux, exécutez Move-CsUser avec le commutateur -MoveToTeams.

    - Si vous transférez des numéros vers Microsoft, vous devez coordonner le moment où cette opération se produit lorsque le port se produit.

    - Si vous utilisez de nouveaux numéros de Microsoft, vous devez modifier l’LineUri de l’utilisateur une fois l’utilisateur déplacé en ligne à l’aide de Set-CsPhoneNumberAssignment.

## <a name="summary-of-per-tenant-configuration-of-direct-routing"></a>Résumé de la configuration par locataire du routage direct

1. Vérifiez que votre contrôleur de frontière de session (SBC) est pris en charge avec le routage direct en examinant [cette liste](direct-routing-border-controllers.md). Vérifiez également que vous disposez de la version correcte du microprogramme.

2. Associez votre SBC local au service de routage direct Teams. Pour plus d’informations, consultez [Associer le SBC au service de routage direct de Système téléphonique](direct-routing-configure.md).

3. Cette configuration est essentiellement un miroir de la configuration locale. La configuration en ligne se compose de :
   - OnlineVoiceRoutingPolicy (basé sur voiceRoutingPolicy local si vous migrez des utilisateurs à partir de Skype Entreprise Online, et sur VoicePolicy si vous migrez des utilisateurs à partir d’un site local avec Voix Entreprise).
   - Objets OnlinePSTNUsage (basés sur l’utilisation locale de PSTN).
   - Objets OnlineVoiceRoute (basés sur VoiceRoute local).

Pour plus d’informations, consultez [Configurer le routage direct](direct-routing-configure.md).

## <a name="manage-enterprisevoiceenabled-property-during-migration"></a>Gérer la propriété EnterpriseVoiceEnabled pendant la migration

Qu’il utilise le routage direct ou un plan d’appel Microsoft, un utilisateur doit avoir EnterpriseVoiceEnabled=true dans Azure AD pour que l’utilisateur dispose des fonctionnalités RTC.  EnterpriseVoiceEnabled (« ev-enabled ») est une propriété (et non une stratégie) qui existe à la fois dans un répertoire local et dans le cloud. La valeur dans le cloud est ce qui compte pour Teams.  La logique exacte de la définition de la valeur true pour EV dépend du scénario suivant :

- Si l’utilisateur est activé pour ev dans un Skype Entreprise Server local et qu’une licence Système téléphonique est attribuée à l’utilisateur avant de déplacer l’utilisateur vers le cloud avec Move-CsUser, l’utilisateur en ligne est approvisionné avec EV-enabled=true.

- Si une licence Système téléphonique est attribuée à un utilisateur TeamsOnly ou Skype Entreprise Online existant, ev n’est pas défini sur true par défaut. C’est également le cas si un utilisateur local est déplacé vers le cloud avant d’attribuer la licence Système téléphonique. Dans les deux cas, l’administrateur doit spécifier l’applet de commande suivante :

  ```PowerShell
  Set-CsPhoneNumberAssignment -EnterpriseVoiceEnabled $True
  ```

## <a name="related-links"></a>Liens connexes

[Planifier votre solution vocale Teams](cloud-voice-landing-page.md)

[Guide de la migration et de l’interopérabilité pour les organisations qui utilisent Teams avec Skype Entreprise](migration-interop-guidance-for-teams-with-skype.md)

[Configurer la connectivité hybride entre Skype Entreprise Server et Microsoft 365 ou Office 365](/SkypeForBusiness/hybrid/configure-hybrid-connectivity)

[Déplacer des utilisateurs entre l’environnement local et le cloud](/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)

[Configuration de vos paramètres de coexistence et de mise à niveau](setting-your-coexistence-and-upgrade-settings.md)

[Grant-CsTeamsUpgradePolicy](/powershell/module/skype/grant-csteamsupgradepolicy)

[Utilisation du service de migration de réunion (MMS)](/skypeforbusiness/audio-conferencing-in-office-365/setting-up-the-meeting-migration-service-mms)
