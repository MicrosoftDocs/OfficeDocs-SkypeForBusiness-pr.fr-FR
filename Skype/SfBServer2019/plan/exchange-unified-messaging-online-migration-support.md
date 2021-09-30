---
title: Prise en charge de la migration en ligne de la messagerie unifiée Exchange
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Microsoft retire le service de messagerie Exchange Online (ExchUMO) d’ici le 28 février 2020. Cet article récapitule ce que les clients concernés doivent savoir et faire pour planifier leur continuité d’activité.
ms.openlocfilehash: 1e6d24b05b8f1c6b8d2b47533edbd9ad79c5022e
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60013288"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Prise en charge de la migration en ligne de la messagerie unifiée Exchange

> [!IMPORTANT]
> **Le service de messagerie unifiée dans Exchange Online n’est plus prise en charge depuis le 28 février 2020, 17 h (heure du Pacifique). Tous les comptes de messagerie vocale ont été migrés vers Messagerie vocale infonuagique service de messagerie vocale par Microsoft. Le trafic restant du service de surveillance automatique n’est pas surveillé et peut être interrompu à tout moment.**

En référence [](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) à l’annonce du 8 février 2019, Microsoft retire le service de messagerie unifiée Exchange Online (ExchUMO) d’ici le 28 février 2020. Cet article récapitule ce que les clients concernés doivent savoir et faire pour planifier leur continuité d’activité.

ExchUMO est déployé par les clients pour les services d’intégration de messagerie vocale, de attendant automatique, de file d’attente d’appels et de télécopie. Microsoft prévoit d’aider les clients à migrer vers Système téléphonique services qui permettent déjà de prendre en charge des milliers de clients sur Skype Entreprise Online et Microsoft Teams.

La messagerie vocale est principalement une migration pilotée par Microsoft . l’implication de l’administrateur et/ou l’investissement peuvent être requis pour un sous-ensemble de clients. Le attendant automatique est une migration pilotée par l’administrateur ; vous devrez re-créer les arbre de attendant automatique ExchUMO existants dans le service cloud Standard automatique cloud. Les clients qui utilisent l’une des fonctionnalités ExchUMO avec un PBX tiers ne seront pas migrés vers les services cloud Skype, car ils ne sont pas en charge les systèmes PBX tiers. Un plan de retrait pour le support tiers a été annoncé dans ce [blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853)et les clients de ce modèle de déploiement peuvent migrer leurs utilisateurs vers l’une des plateformes/services de communications unifiées de Microsoft ou acquérir une solution de messagerie vocale et/ou de standard automatique tierce pour ces utilisateurs. L’intégration des télécopies n’est pas prise en charge dans les services cloud ; les clients devront migrer vers une solution tierce.

## <a name="who-is-affected"></a>Qui est-elle affectée ?

Les clients qui utilisent l’une des fonctionnalités suivantes du service Exchange Messagerie unifiée Online sont affectés :

- Service de messagerie vocale
- Standard automatique service
- Service de file d’attente des appels
- Intégration des télécopies

> [!Note]
> Les clients qui utilisent l’un Exchange Server local avec la messagerie unifiée ne sont pas affectés.

En savoir plus sur l’impact de l’expérience utilisateur et de l’administrateur sur [l’impact sur l’expérience utilisateur.](#user-experience-impact)

## <a name="migration-plan-overview"></a>Vue d’ensemble du plan de migration

Microsoft a identifié différents déploiements de clients qui utilisent des fonctionnalités d’ExchUMO et aidera les clients à migrer en fonction de l’offre suivante.

|Groupe de clients |Chronologie  |Détails  |
|---------|---------|---------|
|Clients prêts à migrer<br><br>Fonctionnalités à migrer :<br><ul><li>Messagerie vocale</ul>   |   Mars - Mai 2019  |Exemples :<ul><li>    Clients avec un déploiement et une utilisation simples de la messagerie vocale<li>Clients pour qui toutes les conditions requises sont établies pour que Microsoft exécute la migration<ul>|
|Clients avec conditions préalables<br><br>Fonctionnalités à migrer :<br><ul><li>Messagerie vocale<li>Standard automatique<li>File d’attente des appels</ul> |  Mai - Décembre 2019 |Exemples : <br><ul><li>La configuration hybride n’est pas terminée<li>Les numéros PSTN hybrides ne sont pas mis en place</ul>|
|Clients qui nécessitent l’implication de l’administrateur & investissement client<br><br>Fonctionnalités à migrer :<ul><li>voicemail<li>Standard automatique<li>Files d’attente d’appels<li>Intégration des télécopies</ul>| D’ici février 2020  | Exemples : <br><ul><li>Le service ExchUMO est consommé par un PBX tiers<li>Clients ayant des exigences d’accès abonné PSTN<li>Clients sur SFB 2010 (non pris en charge)<li>Intégration des télécopies</ul> |

## <a name="voicemail-migration-guidelines"></a>Recommandations en matière de migration de la messagerie vocale

### <a name="get-informed"></a>Être informé

Familiarisez-vous avec l’annonce [du blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) et cet article pour planifier une migration fluide pour vos utilisateurs. Consultez [la Skype Entreprise de messagerie vocale et les options](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) pour plus d’informations sur Système téléphonique fonctionnalités de messagerie vocale.  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Établir une topologie Skype Entreprise hybride

Si aucune topologie hybride Skype Entreprise n’est établie, vous devez le faire pour permettre une migration fluide de vos utilisateurs de messagerie vocale. Pour [plus d’informations, voir Skype Entreprise hybride.](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md)

> [!Note]
> Il n’est pas nécessaire de migrer vos utilisateurs en ligne pour la migration du service de messagerie vocale. Toutefois, pour que les utilisateurs locaux tirent parti Système téléphonique service de messagerie vocale, une topologie hybride doit être établie.

### <a name="plan-your-auto-attendant-migration"></a>Planifier la migration de votre service de attendant automatique

Les administrateurs peuvent commencer à migrer leurs attendants automatiques d’ExchUMO vers le service de gestion automatique cloud à tout moment. Pour [plus d’informations,](/microsoftteams/create-a-phone-system-auto-attendant) voir Configurer un attendant automatique cloud.

Microsoft continue de fournir des fonctionnalités de attendant automatique supplémentaires que les clients peuvent considérer comme requises pour leur migration. Les administrateurs doivent évaluer l’ensemble des fonctionnalités et migrer leurs instances de attendant automatique en conséquence. Pour une comparaison des listes de fonctionnalités, voir la matrice des fonctionnalités [des services cloud ExchUMO](#exchumo-and-azure-cloud-based-services-feature-matrix)et Azure.

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>Planifier la validation et le test de votre messagerie vocale après la migration

La migration de la messagerie vocale est pilotée par Microsoft. Les administrateurs n’ont rien à faire, étant donné que la topologie hybride pré-requise est établie. Microsoft effectue les tests et validations requis pour s’assurer que la migration de la messagerie vocale des utilisateurs n’est pas interrompue. Les administrateurs sont encouragés à effectuer des tests et une validation de leur côté. Voir [Plan de test suggéré et validation post-migration](#suggested-test-plan-and-post-migration-validation-for-admins) pour les administrateurs pour un plan de test recommandé.

> [!Note]
> Lync Server 2010 n’est pas pris en charge. Si vous êtes dans un déploiement de serveur 2010, vous devez planifier une mise à niveau de serveur ou envisager de migrer vos utilisateurs vers Microsoft Teams.  

### <a name="monitor-the-admin-notification-center"></a>Surveiller le Centre de notifications d’administration

Regardez une notification dans le Centre de notifications d’administration avec des détails supplémentaires et une chronologie concernant la migration de vos utilisateurs. Les notifications sont envoyées au moins 30 jours avant votre période de migration.

> [!Note]
> Si vous avez reçu une notification avec la chronologie de migration de vos utilisateurs et que vous souhaitez différer votre migration pour une raison critique pour l’entreprise, vous pouvez le faire en contactant le Support Microsoft. Vous ne pouvez pas reporter votre migration au-delà de la date de retrait du 28 février 2020. Pour les clients qui peuvent avoir d’autres questions, contactez votre équipe de compte ou le Support Microsoft. Les clients qui utilisent Microsoft 365 ou Office 365 peuvent soumettre un dossier de support via le Centre d'administration Microsoft 365.

### <a name="consider-opting-in-for-a-planned-migration"></a>Envisager d’opter pour une migration planifiée

Vous pouvez opter pour une migration planifiée du service de messagerie vocale vers la gestion des cvm. Avant d’opter, examinez les détails de cet article, en particulier les sections suivantes :

- Étapes de migration (cette section)
- Matrice des fonctionnalités des services cloud ExchUMO et Azure
- Impact sur l’expérience utilisateur

Lorsque vous choisissez une migration gérée, vous ne recevrez pas de notification préalable à la migration de 30 jours dans le centre de messages Microsoft 365 d’administration.

Pour opter pour une migration planifiée, envoyez une demande de courrier électronique à partir de l’adresse de messagerie de votre administrateur [cvm@microsoft.com](mailto:cvm@microsoft.com) avec les informations suivantes :

- Date préférée (mardis) : les vagues de migration sont exécutées tous les mardis. Veuillez sélectionner une date le mardi qui n’est pas au-delà du 3/12/2019.
 
- ID client : 32 caractères au format 0046728c-688a-4472-a38f-098fec60ac6x. Vous pouvez trouver votre ID de client dans le portail d’administration Microsoft 365 sous Azure AD, ou à l’aide de l’cmdlet PowerShell suivante :`Get-CsTenant | Select ObjectId`

Vous recevrez une confirmation par courrier électronique une fois votre client correctement migré.

## <a name="auto-attendant-migration-guidelines"></a>Instructions de migration du service de sécurité automatique

Les administrateurs d’Microsoft 365 et d’Office 365 sont tenus de créer à nouveau leurs standard automatiques Exchange UM Online dans le service Microsoft Cloud Standard automatique et de leur changer leurs numéros de téléphone locaux avant la date de retrait du service UMO Exchange du 28 février 2020. Il s’agit de la recommandation pour réussir la migration et le test de nouveaux attendants automatiques cloud. Si vous avez un grand nombre de attendants automatiques, vous pouvez utiliser les [scripts Standard automatique](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) de migration de la Standard automatique de la Exchange vers cloud Standard automatique pour simplifier la migration en bloc des attendants automatiques.

### <a name="auto-attendant-setup"></a>Configuration du standard automatique

Nous vous conseillons vivement de commencer la configuration de vos nouveaux attendants automatiques tôt pour éviter les problèmes de dernière minute et pour vous familiariser avec les fonctionnalités et l’expérience du service Cloud Standard automatique. Pour les attendants automatiques qui nécessitent une ou plusieurs fonctionnalités d’intervalle, vous pouvez créer et tester les attendants automatiques lorsque les fonctionnalités d’intervalle sont disponibles pour préparer le déploiement. Pour plus d’informations sur les fonctionnalités d’écart, consultez [l’Annexe.](#appendix)

1. Utilisez les Exchange UMO pour exporter la configuration des attendants automatiques existants à l’aide de [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant).  

2. Utilisez la cmdlet [Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt) dans Exchange Online PowerShell pour exporter les fichiers multimédias de message d’accueil (s’ils sont utilisés) et les convertir au format .mp3 format.

3. Suivez les instructions de [Plan Cloud auto attendants](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) and [Set up a Cloud auto attendant](/microsoftteams/create-a-phone-system-auto-attendant) to create auto attendants by using the Microsoft Teams admin center or PowerShell.

4. Examinez vos message d’accueil si les options de menu ont été modifiées.

5. Configurez les [transferts](#known-issues) vers vos groupes Response Groups à l’aide de la solution de contournement « Standard automatique Call Transfer to PSTN » dans la section Problèmes connus de cet article.  

6. Testez les nouveaux attendants automatiques en les appelant en interne ou en attribuant un numéro de téléphone de test.  

### <a name="cutover"></a>Basculement

1. Basculez vos numéros de téléphone Exchange des standard automatiques UMO vers les nouveaux standard automatiques.
2. Déplacez l’URI SIP de l’objet contact vers le compte de ressource.
3. Testez et validez vos numéros de téléphone automatiques à l’aide des numéros de téléphone nouvellement affectés.

## <a name="appendix"></a>Annexe

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matrice des fonctionnalités des services cloud ExchUMO et Azure

| Service | Niveau de fonctionnalité | Fonctionnalité | Notes  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Fonctionnalités de service| Prise en charge du PBX tiers    | Inclure toutes les fonctionnalités fournies aux PBX tiers, telles que l’indicateur de message en attente (MWI) à l’aide de SIP, pour notifier les messages Exchange de la Exchange en ligne | N   | O    |
| VM | Fonctionnalités de service  | Prise en charge Skype Entreprise Server   |  | v | v    |
| VM | Fonctionnalités de service | Prise en charge Microsoft Teams|  | v | N    |
| VM | Fonctionnalités de service | eDiscovery et hold  | Pour la sécurité et la conformité  | v | v    |
| VM | Fonctionnalités de service | Exchange Prise en charge des règles | Pour la sécurité et la conformité  | v | v    |
| VM | Fonctionnalités utilisateur | Accès à la numérotation PSTN  | Accès abonné  | N | O    |
| VM | Fonctionnalités utilisateur | Délégué  | e-mail d’appel manqué  | N | O    |
| VM | Fonctionnalités utilisateur | Accès vocal Outlook PSTN   | Accès abonné  | N | O    |
| VM | Fonctionnalités utilisateur | Numérotation à l’aide d’un point de terminaison authentifié | Appel du service de messagerie vocale pour écouter les messages vocaux et modifier les paramètres de messagerie vocale| v | v    |
| VM | Fonctionnalités utilisateur | Paramètre utilisateur pour désactiver la messagerie vocale   |  | v | v    |
| VM | Fonctionnalités utilisateur | Paramètre utilisateur pour modifier le message d’accueil personnel  |  | v | v    |
| VM | Fonctionnalités utilisateur | Paramètre utilisateur pour créer un message d’accueil de l’absence du système  |  | v | v    |
| VM | Fonctionnalités utilisateur | Paramètre utilisateur pour modifier la langue par défaut  |  | v | v    |
| VM | Fonctionnalités utilisateur | Paramètre utilisateur pour la réécriture du message d’accueil par défaut avec TTS  |  | v | N    |
| VM | Fonctionnalités utilisateur | Enregistrer des message d’accueil personnels (appareil authentifié) |  | v | v    |
| VM | Fonctionnalités utilisateur | Enregistrer des salutations personnelles (PSTN) : lire sur le téléphone |  | N | O    |
| VM | Fonctionnalités utilisateur | Paramètre utilisateur pour désactiver la transcription |  | N | O    |
| VM | Fonctionnalités utilisateur | Transcription  |  | v | v    |
| VM | Fonctionnalités utilisateur | Indicateur de message en attente (MWI) à l’aide de messages notifiés SIP |  | N | O    |
| VM | Fonctionnalités utilisateur | Format de fichier audio MP3 dans Outlook    |  | v | v    |
| VM | Fonctionnalités utilisateur | Contrôle de lecture de vitesse variable |  | v | v    |
| VM | Fonctionnalités utilisateur | Forward a voicemail  | Forward a received voicemail to other users | v | v    |
| VM | Fonctionnalités utilisateur | Envoi d’un message vocal à un groupe d’utilisateurs  |Diffusion de messagerie vocale   | N | O   |
| VM | Fonctionnalités utilisateur | Notification de messagerie vocale à l’aide de SMS    | Les utilisateurs peuvent recevoir un SMS lorsqu’ils ont un nouveau message vocal    | N | O    |
| VM | Fonctionnalités utilisateur | Langues d’accueil prise en charge | Détails ici : [Qu’est-ce que les attendants automatiques cloud ?](/microsoftteams/what-are-phone-system-auto-attendants) | v | v    |
| VM | Fonctionnalités utilisateur | Règles de répondeur automatique |  | v | v    |
| VM | Fonctionnalités utilisateur | Lire sur le téléphone (PSTN) : lire un message | M’appeler sur ma cellule pour écouter le message vocal  | N | O    |
| VM | Fonctionnalités utilisateur | Lire sur le téléphone (th)- pour lire un message | M’appeler sur mon appareil authentifié  | N | O    |
| VM | Fonctionnalités utilisateur | Boîte aux lettres partagée entre plusieurs utilisateurs |  | v | v    |
| VM | Fonctionnalités de l’appelant  | Expérience de l’appelant : messagerie vocale protégée | L’appelant peut choisir une option pour marquer un message enregistré comme protégé| N | O    |
| VM | Fonctionnalités de l’appelant  | Expérience de l’appelant : messagerie vocale privée | L’appelant peut choisir une option pour marquer un message enregistré comme privé  | N | O    |
| VM | Fonctionnalités de l’appelant  | Détection du silence   |  | N | O    |
| VM | Tenant-Admin fonctionnalités | Messagerie vocale protégée au niveau du serveur    | L’administrateur client peut configurer une règle de niveau de service pour marquer la messagerie vocale entrante comme étant protégée | v | v    |
| VM | Tenant-Admin fonctionnalités | Modifier la durée limite de l’enregistrement  |     | v | v    |
| VM | Tenant-Admin fonctionnalités | Modifier le délai d’out de détection du silence    |  | S/O    | O    |
| VM | Tenant-Admin fonctionnalités | Modifier le nombre d’échecs d’entrée | CVM : codé en dur sur 3 | N | O    |
| VM | Tenant-Admin fonctionnalités | Modifier la langue par défaut |  | v | v    |
| VM | Tenant-Admin fonctionnalités | Désactiver/activer la transcription |  | v | v    |
| VM | Tenant-Admin fonctionnalités | Désactiver/activer la notification d’appel manqué |  | N | O    |
| VM | Tenant-Admin fonctionnalités | Aider Microsoft à améliorer l'aperçu de messagerie vocale    |  | v | v    |
| VM | Tenant-Admin fonctionnalités | Personnaliser le message texte pour les utilisateurs activés|  | S/O    | O    |
| VM | Tenant-Admin fonctionnalités | Masquage de la transcription|  | v | N    |
| VM | Tenant-Admin fonctionnalités | Stratégie de messagerie vocale    |   | v | v    |
| VM | Tenant-Admin fonctionnalités | Administration du portail web   |  | CY19   | O    |
| VM | Tenant-Admin fonctionnalités | PowerShell   |  | v | v    |
| UM | Fonctionnalités utilisateur | Indicateur de message en attente (MWI) sur Skype Entreprise téléphones certifiés   |Peut être fourni par un partenaire téléphonique  | Non | Oui    |
| AA | Fonctionnalités de service | AA support 3rd-party PBX    |  | N | O    |
| AA | Fonctionnalités de service | Prise en charge Skype Entreprise Server   |  | v | v    |
| AA | Fonctionnalités de service | Prise en charge Microsoft Teams|  | v | N    |
| AA | Fonctionnalités de service | Numérotation par nom, entrée DTMF    |  | v | v    |
| AA | Fonctionnalités de service | Numérotation par nom, saisie vocale  |  | v | v    |
| AA | Fonctionnalités de service | Prise en charge multi-langue | Détails linguistiques ici : [qu’est-ce que les attendants automatiques cloud ?](/microsoftteams/what-are-phone-system-auto-attendants) | v | v    |
| AA | Fonctionnalités de service | Transférer vers un opérateur, un CQ ou un utilisateur |  | v | v    |
| AA | Fonctionnalités de service | Transférer vers le numéro PSTN en interne (DID RNL)  |  | v | v    |
| AA | Fonctionnalités de service | Transférer vers le numéro PSTN en externe  |  | Consultez la section Problèmes connus ci-dessous | O    |
| AA | Fonctionnalités de service | Heures d'ouverture |  | v | v    |
| AA | Fonctionnalités de service | Options de menu | Options de menu du système de réponse vocale vocale (IVR)  | v | v    |
| AA | Fonctionnalités de service | Affectation d’un numéro RSTN cloud à AA |  | v | N    |
| AA | Fonctionnalités de service | Affectation d’un numéro PSTN sur place à AA  |  | v | v    |
| AA | Fonctionnalités de service | Sélection personnalisée de l’utilisateur  | Permettre aux appelants d’atteindre une liste personnalisée d’utilisateurs de l’organisation| v | v    |
| AA | Fonctionnalités de service | Traitement des heures supplémentaires et des jours fériés  |  | v | v    |
| AA | Fonctionnalités de service | Message d’accueil personnalisé utilisant la reconnaissance vocale  |  | v | v    |
| AA | Fonctionnalités de service | Numérotation d’extension   | Atteindre un utilisateur en composant son poste  | v   | v    |
| AA | Fonctionnalités de service | Boîte aux lettres pour que les appelants AA laissent un message    |  | v   | v    |
| AA | Fonctionnalités de service | Affectations de plusieurs nombres PSTN à une AA|  | v | v    |
| AA | Tenant-Admin fonctionnalités | Administration du portail web   |  | v | N    |
| AA | Tenant-Admin fonctionnalités | Cmdlets PowerShell  |  | v | v    |
| Fax| Fonctionnalités de service | Intégration des télécopies|  | N | O    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plan de test suggéré et validation post-migration pour les administrateurs

Pour vérifier que vos utilisateurs ont été migrés vers Messagerie vocale infonuagique, laissez une messagerie vocale à un utilisateur et vérifiez le corps du message dans Outlook. Messagerie vocale infonuagique messages ont un pied de groupe qui lit :

« Merci d’avoir utilisé la transcription ! Si vous ne voyez pas de transcription ci-dessus, c’est parce que la qualité audio n’était pas suffisamment claire pour transcrire. »

Lorsque vous testez la fonctionnalité de messagerie vocale après la migration de vos utilisateurs, prenez en compte les scénarios suivants :

- Valider l’accès à la messagerie vocale sur tous les types de points de terminaison de votre organisation, tels que les applications et les téléphones IP.
- Validez avec des exemples d’utilisateurs que les messages d’accueil personnalisés configurés sont lésés aux appelants.
- Si votre organisation a une obligation légale ou de conformité de désactiver la transcription pour les utilisateurs, assurez-vous qu’elle est désactivée après la migration. Pour plus d’informations, voir [Messagerie vocale infonuagique](/microsoftteams/set-up-phone-system-voicemail).
- Si vous avez précédemment configuré des Exchange et des règles de la VM, assurez-vous qu’elles sont efficaces.
- Familiarisez-vous avec les cmdlets PowerShell Messagerie vocale infonuagique service pour modifier les paramètres utilisateur.  

### <a name="user-experience-impact"></a>Impact sur l’expérience utilisateur

Voici une vue d’ensemble de l’expérience de migration de la messagerie vocale pour l’utilisateur final.


|Expérience  |Modification de l’expérience utilisateur|
|---------|---------|
|Notification par courrier électronique | Aucune modification<br>Aucun message électronique n’est envoyé aux utilisateurs pour les informer de l’activation/migration du compte de messagerie vocale. |
|Accès aux messages précédents | Aucune modification<br>Les utilisateurs ont accès à leurs messages vocaux précédents dans tous les points de terminaison pris en charge. |
|Réception d’une VM dans outlook, applications SFB| Aucune modification<br>Les utilisateurs continuent de recevoir leurs messages vocaux dans tous les points de terminaison pris en charge. |
|Transcription | Amélioré<br>La transcription CVM présente un taux de précision et des langues pris en charge beaucoup plus élevé que ExchUMO. |
|Paramètre utilisateur | Nouvelle expérience<br>Les utilisateurs peuvent modifier leurs préférences à partir d’un portail de paramètres utilisateur (USP). Les utilisateurs peuvent accéder à leur usp à partir d’un lien hypertexte dans leur messagerie vocale ou du bouton User-Settings sur leur client SFB ; https://aka.ms/vmsettings.
 |Fonctionnalités| Pour plus d’informations, voir la comparaison des ensembles de fonctionnalités. |
|Outlook pour les messages de la VM | Aucune modification<br>Les règles créées précédemment s’appliquent aux messages de gestion des cvm après la migration.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>Gestion des utilisateurs et approvisionnement dans la gestion des cvm

Les Skype Entreprise utilisateurs seront automatiquement mis en service pour la messagerie vocale cloud lors de leur création. Aucune licence ou travail d’administrateur supplémentaire n’est requis pour mettre en service de nouveaux utilisateurs de messagerie vocale. Voir [Configurer Messagerie vocale infonuagique](/microsoftteams/set-up-phone-system-voicemail) pour en savoir plus sur la gestion des stratégies pour les utilisateurs existants et nouveaux.

### <a name="admin-auto-attendant-management-experience"></a>Expérience de gestion Standard automatique administrateur

Pour en savoir plus sur les attendants automatiques, voir [Configurer un attendant automatique cloud.](/microsoftteams/create-a-phone-system-auto-attendant)

### <a name="known-issues"></a>Problèmes connus

#### <a name="greeting-inconsistencies"></a>Incohérences de message d’accueil

L’accès abonné peut continuer à fonctionner pour votre client jusqu’à ce que le service soit complètement retiré, même après que tous vos utilisateurs ont été migrés vers Messagerie vocale infonuagique. Pour éviter toute confusion chez l’utilisateur et une expérience incohérente, désactivez l’accès abonné car les salutations changent après la migration. Pour ce faire, supprimez le contact EXUM pour chaque ligne d’accès abonné à l’aide `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` de .

#### <a name="auto-attendant-call-transfer-to-pstn"></a>Standard automatique transfert d’appel vers PSTN

Pour transférer un appel de attendant automatique vers un numéro de téléphone PSTN externe via Skype Entreprise Server ou un service Response Group (RGS) sur Skype Entreprise Server, créez un utilisateur local avec le transfert d’appel sur le numéro de téléphone RGPD ou le numéro de téléphone RGS. L’utilisateur doit être activé et correctement configuré pour Voix Entreprise et une stratégie de voix doit être affectée.

#### <a name="shared-mailbox-is-still-accessible"></a>La boîte aux lettres partagée est toujours accessible

Une boîte aux lettres partagée configurée à l’aide de Exchange um Online continue de recevoir des messages après la migration vers la gestion des cvm et d’être accessible aux utilisateurs via Outlook. Toutefois, l’accès à la modification des messages d’accueil de ces boîtes aux lettres ne sera pas disponible une fois migrés vers la cvm. Les clients ayant des boîtes aux lettres partagées qui sont utilisées pour capturer des appelants de attendant automatique doivent tirer parti des fonctionnalités de boîtes aux lettres partagées des files d’attente d’appel et des attendants automatiques une fois publiées (ETA octobre 2019).
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>La bannière « Le nom d’utilisateur n’utilise Skype Entreprise » s’affiche

Le service CVM est basé sur l’infrastructure Microsoft Teams et les appels d’un client Skype Entreprise peuvent entraîner l’affichage d’une bannière d’informations sur le client qui indique : « Le nom d’utilisateur n’utilise pas Skype Entreprise. Pour une expérience plus riche, basculez vers Teams ou démarrez une Skype réunion. »
Veillez à mettre à jour le client Skype Entreprise utilisateur vers la dernière mise à jour du client C2R pour empêcher l’apparition de cette bannière.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>« Configurer la messagerie vocale » vous OWA

Si  vous cliquez sur Configurer la messagerie vocale à partir du client, les clients Skype Entreprise Server 2015/2013 accèdent à la page du portail Office Web Access (OWA) après la migration vers la gestion des cvm. Tous les paramètres ont été supprimés de l’onglet Messagerie vocale dans OWA et une bannière s’affiche avec un lien de redirection pour rediriger les utilisateurs vers le portail des paramètres utilisateur de la cvm.

#### <a name="changing-greeting-remotely"></a>Modification du message d’accueil à distance

L’accès abonné PSTN n’est pas pris en charge dans la cvm. Pour les utilisateurs qui doivent modifier leur message d’accueil à distance, une option de menu « Modifier votre message d’accueil » a été ajoutée au service de réponse vocale pour les clients mobiles. Les utilisateurs peuvent appeler ce service en appuyant sur la touche « 1 » et en maintenant la touche « 1 » sur le pavé de numérotation du client mobile.