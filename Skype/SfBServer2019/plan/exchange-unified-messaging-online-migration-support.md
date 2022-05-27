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
description: Microsoft met hors service Exchange Messagerie unifiée en ligne (ExchUMO) d’ici le 28 février 2020. Cet article récapitule ce que les clients concernés doivent savoir et faire pour planifier leur continuité d’activité.
ms.openlocfilehash: d9e041516f06b5ce5ddf4e411b261bf99a9703f9
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65676366"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Prise en charge de la migration en ligne de la messagerie unifiée Exchange

> [!IMPORTANT]
> **Le service de messagerie unifiée dans Exchange Online n’est plus pris en charge depuis le 28 février 2020, 17h00 heure du Pacifique. Tous les comptes de messagerie vocale ont été migrés vers Messagerie vocale infonuagique service par Microsoft. Tout trafic de standard automatique restant n’est pas surveillé et peut être interrompu à tout moment.**

En référence à [l’annonce](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) du 8 février 2019, Microsoft met hors service Exchange messagerie unifiée en ligne (ExchUMO) d’ici le 28 février 2020. Cet article fournit un résumé de ce que les clients concernés doivent savoir et faire pour planifier leur continuité d’activité.

ExchUMO est déployé par les clients pour les services d’intégration de messagerie vocale, de standard automatique, de file d’attente d’appels et de télécopie. Microsoft prévoit d’aider les clients à migrer vers Système téléphonique services qui prennent déjà en charge des milliers de clients sur Skype Entreprise Online et Microsoft Teams.

La messagerie vocale est principalement une migration pilotée par Microsoft; l’implication de l’administrateur et/ou un investissement peut être nécessaire pour un sous-ensemble de clients. Le standard automatique est une migration pilotée par l’administrateur ; vous devez recréer les arborescences de standard automatique ExchUMO existantes dans le service cloud Cloud Auto Attendant. Les clients qui consomment l’une des fonctionnalités ExchUMO avec un PBX tiers ne seront pas migrés vers Skype services cloud, car ils ne prennent pas en charge les systèmes PBX tiers. Un plan de mise hors service pour le support tiers a été annoncé dans [ce blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853), et les clients de ce modèle de déploiement peuvent migrer leurs utilisateurs vers l’une des plateformes/services de communications unifiées de Microsoft ou acquérir une solution tierce de messagerie vocale et/ou de standard automatique pour ces utilisateurs. L’intégration de télécopie n’est pas prise en charge dans les services cloud ; devront migrer vers une solution tierce.

## <a name="who-is-affected"></a>Qui est affecté ?

Les clients qui utilisent l’une des fonctionnalités suivantes du Exchange service Unified Messaging Online sont affectés :

- Service de messagerie vocale
- Service standard automatique
- Service de file d’attente d’appels
- Intégration de télécopie

> [!Note]
> Les clients qui utilisent l’un des Exchange Server locaux avec la messagerie unifiée ne sont pas affectés.

En savoir plus sur l’impact de l’expérience utilisateur et administrateur sur [l’impact de l’expérience utilisateur](#user-experience-impact).

## <a name="migration-plan-overview"></a>Vue d’ensemble du plan de migration

Microsoft a identifié différents déploiements de clients qui consomment des fonctionnalités d’ExchUMO et aidera les clients à migrer en fonction du plan suivant.

|Groupe de clients |Chronologie  |Détails  |
|---------|---------|---------|
|Clients prêts à migrer<br><br>Fonctionnalités à migrer :<br><ul><li>Messagerie vocale</ul>   |   mars — mai 2019  |Exemples :<ul><li>    Clients disposant d’un déploiement et d’une utilisation de messagerie vocale simples<li>Clients qui ont toutes les exigences établies pour que Microsoft exécute la migration<ul>|
|Clients avec prérequis<br><br>Fonctionnalités à migrer :<br><ul><li>Messagerie vocale<li>Standard automatique<li>File d’attente d’appels</ul> |  mai — décembre 2019 |Exemples : <br><ul><li>La configuration hybride n’est pas terminée<li>Les numéros RTC hybrides ne sont pas configurés</ul>|
|Clients qui ont besoin d’une participation de l’administrateur & investissement des clients<br><br>Fonctionnalités à migrer :<ul><li>voicemail<li>Standard automatique<li>Files d'attente des appels<li>Intégration de télécopie</ul>| D’ici février 2020  | Exemples : <br><ul><li>Le service ExchUMO est consommé par pbX tiers<li>Clients ayant des exigences d’accès aux abonnés RTC<li>Clients sur SFB 2010 (non pris en charge)<li>Intégration de télécopie</ul> |

## <a name="voicemail-migration-guidelines"></a>Instructions relatives à la migration de la messagerie vocale

### <a name="get-informed"></a>S’informer

Familiarisez-vous avec [l’annonce de blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) et cet article pour planifier une migration fluide pour vos utilisateurs. Pour plus d’informations sur les fonctionnalités de messagerie [vocale Système téléphonique, consultez La messagerie vocale Skype Entreprise et les options](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8).  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Établir une topologie hybride Skype Entreprise

Si vous n’avez pas de topologie hybride Skype Entreprise établie, vous devez le faire pour permettre une migration fluide de vos utilisateurs de messagerie vocale. Pour plus d’informations, consultez [Configurer Skype Entreprise hybride](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md).

> [!Note]
> Vous n’avez pas besoin de migrer vos utilisateurs en ligne pour la migration du service de messagerie vocale. Toutefois, pour que les utilisateurs locaux puissent tirer parti Système téléphonique service de messagerie vocale, une topologie hybride doit être établie.

### <a name="plan-your-auto-attendant-migration"></a>Planifier la migration de votre standard automatique

Les administrateurs peuvent commencer à migrer leurs standards automatiques d’ExchUMO vers le standard automatique cloud à tout moment. Pour plus d’informations, consultez [Configurer un standard automatique cloud](/microsoftteams/create-a-phone-system-auto-attendant) .

Microsoft continue de fournir des fonctionnalités de standard automatique supplémentaires que les clients peuvent considérer nécessaires pour leur migration. Les administrateurs doivent évaluer l’ensemble de fonctionnalités et migrer leurs instances de standard automatique en conséquence. Pour une comparaison de listes de fonctionnalités, consultez la [matrice des fonctionnalités des services cloud ExchUMO et Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>Planifier la validation et les tests de votre messagerie vocale après la migration

La migration de la messagerie vocale est pilotée par Microsoft. Les administrateurs ne sont pas tenus de faire quoi que ce soit, étant donné que la topologie hybride prérequise est établie. Microsoft effectue la validation et les tests nécessaires pour s’assurer que la migration de la messagerie vocale des utilisateurs n’est pas interrompue. Les administrateurs sont encouragés à effectuer des tests et des validations de leur côté. Consultez [Le plan de test suggéré et la validation après la migration pour les administrateurs](#suggested-test-plan-and-post-migration-validation-for-admins) pour un plan de test recommandé.

> [!Note]
> Lync Server 2010 n’est pas pris en charge. Si vous êtes dans un déploiement de serveur 2010, vous devez planifier une mise à niveau du serveur ou envisager de migrer vos utilisateurs vers Microsoft Teams.  

### <a name="monitor-the-admin-notification-center"></a>Surveiller le Centre de notification Administration

Recherchez un avis dans le centre de notifications Administration avec des détails supplémentaires et une chronologie concernant la migration de vos utilisateurs. Les notifications sont envoyées au moins 30 jours avant votre période de migration.

> [!Note]
> Si vous avez reçu une notification avec la chronologie de migration de vos utilisateurs et souhaitez reporter votre migration pour une raison critique pour l’entreprise, vous pouvez le faire en contactant Support Microsoft. Vous ne pouvez pas reporter votre migration au-delà de la date de mise hors service du 28 février 2020. Pour les clients susceptibles d’avoir d’autres questions, contactez votre équipe de compte ou Support Microsoft. Les clients qui utilisent déjà Microsoft 365 ou Office 365 peuvent soumettre un cas de support via le Centre d'administration Microsoft 365.

### <a name="consider-opting-in-for-a-planned-migration"></a>Envisagez d’opter pour une migration planifiée

Vous pouvez opter pour une migration planifiée du service de messagerie vocale vers une machine virtuelle virtuelle. Avant de vous inscrire, passez en revue les détails de cet article, en particulier les sections suivantes :

- Étapes de migration (cette section)
- Matrice de fonctionnalités des services cloud ExchUMO et Azure
- Impact de l’expérience utilisateur

Lorsque vous choisissez une migration managée, vous ne recevez pas de notification de prémigrement de 30 jours dans le centre de messages du portail d’administration Microsoft 365.

Pour accepter une migration planifiée, envoyez une demande par e-mail de l’adresse e-mail de votre administrateur à [cvm@microsoft.com](mailto:cvm@microsoft.com) avec les informations suivantes :

- Date préférée (mardi) : les vagues de migration sont exécutées tous les mardis. Sélectionnez une date le mardi qui n’est pas au-delà du 03/12/2019.
 
- ID de locataire : numéro de 32 caractères au format 0046728c-688a-4472-a38f-098fec60ac6x. Vous pouvez trouver votre ID de locataire dans le portail d’administration Microsoft 365 sous Azure AD, ou à l’aide de l’applet de commande PowerShell suivante :`Get-CsTenant | Select ObjectId`

Vous recevrez une confirmation par e-mail une fois que votre locataire aura été correctement migré.

## <a name="auto-attendant-migration-guidelines"></a>Instructions de migration du standard automatique

Microsoft 365 et les administrateurs d’organisation Office 365 sont tenus de recréer leurs standards automatiques um Online Exchange dans le service Microsoft Cloud Auto Attendant et de leur attribuer leurs numéros de téléphone locaux avant la date de mise hors service UMO Exchange le 28 février 2020. Il s’agit de la recommandation recommandée pour réussir la migration et le test de nouveaux standards automatiques cloud. Si vous avez un grand nombre de standards automatiques, vous pouvez utiliser le [Exchange scripts de migration du standard automatique de messagerie unifiée vers le standard automatique cloud](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) pour simplifier la migration en bloc des standards automatiques.

### <a name="auto-attendant-setup"></a>Configuration du standard automatique

Nous vous recommandons vivement de commencer la configuration de vos nouveaux standards automatiques tôt pour éviter les problèmes de dernière minute et pour vous familiariser avec les fonctionnalités et l’expérience du service de standard automatique cloud. Pour les standards automatiques qui nécessitent une ou plusieurs fonctionnalités d’écart, vous pouvez créer et tester les standards automatiques lorsque les fonctionnalités d’écart sont disponibles pour préparer le déploiement. Pour plus d’informations sur les fonctionnalités d’écart, consultez [l’Annexe](#appendix).

1. Utilisez les applets de commande UMO Exchange pour exporter la configuration des standards automatiques existants à l’aide de [Get-UMAutoAttendant](/powershell/module/exchange/unified-messaging/get-umautoattendant).  

2. Utilisez l’applet [de commande Export-UMprompt](/powershell/module/exchange/unified-messaging/export-umprompt) dans Exchange Online PowerShell pour exporter les fichiers multimédias de message d’accueil (s’ils sont utilisés) et les convertir au format .mp3.

3. Suivez les instructions [fournies dans Planifier les standards automatiques cloud](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) et [configurez un standard automatique cloud](/microsoftteams/create-a-phone-system-auto-attendant) pour créer des standards automatiques à l’aide du centre d’administration Microsoft Teams ou de PowerShell.

4. Passez en revue vos salutations si les options de menu ont changé.

5. Configurez les transferts vers vos groupes de réponses à l’aide de la solution de contournement « Transfert d’appel du standard automatique vers RTC » dans la section [Problèmes connus](#known-issues) de cet article.  

6. Testez les nouveaux standards automatiques en les appelant en interne ou en attribuant un numéro de téléphone de test.  

### <a name="cutover"></a>Basculement

1. Basculez vos numéros de téléphone de Exchange standards automatiques UMO vers les nouveaux standards automatiques.
2. Déplacez l’URI SIP de l’objet contact vers le compte de ressource.
3. Testez et validez vos standards automatiques à l’aide des numéros de téléphone nouvellement attribués.

## <a name="appendix"></a>Annexe

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matrice de fonctionnalités des services cloud ExchUMO et Azure

| Service | Niveau de fonctionnalité | Fonctionnalité | Notes  | Machine virtuelle cloud/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| VM  | Fonctionnalités du service| Prise en charge de PBX tiers    | Inclusion de toutes les fonctionnalités fournies à pbX tiers, telles que MWI (indicateur d’attente de messages) à l’aide de sip notifier les messages de Exchange UM Online | N   | v    |
| VM | Fonctionnalités du service  | Skype Entreprise Server de support   |  | v | v    |
| VM | Fonctionnalités du service | Prise en charge Microsoft Teams|  | v | N    |
| VM | Fonctionnalités du service | eDiscovery et Hold  | Pour la sécurité et la conformité  | v | v    |
| VM | Fonctionnalités du service | prise en charge des règles Exchange | Pour la sécurité et la conformité  | v | v    |
| VM | Fonctionnalités utilisateur | Accès rendez-vous RTC  | Accès de l’abonné  | N | v    |
| VM | Fonctionnalités utilisateur | Délégué  | e-mail d’appel manqué  | N | v    |
| VM | Fonctionnalités utilisateur | Outlook Voice Access RTC   | Accès de l’abonné  | N | v    |
| VM | Fonctionnalités utilisateur | Connexion à l’aide d’un point de terminaison authentifié | Appel du service de messagerie vocale pour écouter les messages vocaux et modifier les paramètres de messagerie vocale| v | v    |
| VM | Fonctionnalités utilisateur | Paramètre utilisateur pour désactiver la messagerie vocale   |  | v | v    |
| VM | Fonctionnalités utilisateur | Paramètre utilisateur pour modifier le message d’accueil personnel  |  | v | v    |
| VM | Fonctionnalités utilisateur | Paramètre utilisateur pour créer un message d’accueil OOF  |  | v | v    |
| VM | Fonctionnalités utilisateur | Paramètre utilisateur pour modifier la langue par défaut  |  | v | v    |
| VM | Fonctionnalités utilisateur | Paramètre utilisateur pour remplacer le message d’accueil par défaut avec TTS  |  | v | N    |
| VM | Fonctionnalités utilisateur | Enregistrer les messages d’accueil personnels (appareil authentifié) |  | v | v    |
| VM | Fonctionnalités utilisateur | Enregistrer les messages d’accueil personnels (RTC) : lecture sur téléphone |  | N | v    |
| VM | Fonctionnalités utilisateur | Paramètre utilisateur pour désactiver la transcription |  | N | v    |
| VM | Fonctionnalités utilisateur | Transcription  |  | v | v    |
| VM | Fonctionnalités utilisateur | MWI (indicateur d’attente de messages) à l’aide des messages de notification SIP |  | N | v    |
| VM | Fonctionnalités utilisateur | Format de fichier audio MP3 dans Outlook    |  | v | v    |
| VM | Fonctionnalités utilisateur | Contrôle de lecture de vitesse variable |  | v | v    |
| VM | Fonctionnalités utilisateur | Transférer une messagerie vocale  | Transférer une messagerie vocale reçue à d’autres utilisateurs | v | v    |
| VM | Fonctionnalités utilisateur | Envoi d’un message vocal à un groupe d’utilisateurs  |Diffusion de la messagerie vocale   | N | v   |
| VM | Fonctionnalités utilisateur | Notification de messagerie vocale à l’aide de SMS    | Les utilisateurs peuvent recevoir une SMS lorsqu’ils disposent d’une nouvelle messagerie vocale    | N | v    |
| VM | Fonctionnalités utilisateur | Langues d’accueil prises en charge | Détails ici : [Qu’est-ce que les standards automatiques cloud ?](/microsoftteams/what-are-phone-system-auto-attendants) | v | v    |
| VM | Fonctionnalités utilisateur | Règles de répondeur automatique |  | v | v    |
| VM | Fonctionnalités utilisateur | Lire sur téléphone (RTC) - pour lire le message | Appelez-moi sur ma cellule pour écouter le message vocal  | N | v    |
| VM | Fonctionnalités utilisateur | Lire sur le téléphone (authentification) - pour lire le message | M’appeler sur mon appareil authentifié  | N | v    |
| VM | Fonctionnalités utilisateur | Boîte aux lettres partagée entre plusieurs utilisateurs |  | v | v    |
| VM | Fonctionnalités de l’appelant  | Expérience de l’appelant : messagerie vocale protégée | L’appelant peut choisir une option pour marquer un message enregistré comme protégé| N | v    |
| VM | Fonctionnalités de l’appelant  | Expérience de l’appelant : messagerie vocale privée | L’appelant peut choisir une option pour marquer un message enregistré comme privé  | N | v    |
| VM | Fonctionnalités de l’appelant  | Détection du silence   |  | N | v    |
| VM | fonctionnalités Tenant-Admin | Messagerie vocale protégée au niveau du serveur    | L’administrateur client peut configurer une règle de niveau de service pour marquer la messagerie vocale entrante comme protégée | v | v    |
| VM | fonctionnalités Tenant-Admin | Modifier la durée d’enregistrement  |     | v | v    |
| VM | fonctionnalités Tenant-Admin | Délai d’expiration de la détection du silence des modifications    |  | S/O    | v    |
| VM | fonctionnalités Tenant-Admin | Modifier le nombre d’échecs d’entrée | Machine virtuelle : codée en dur sur 3 | N | v    |
| VM | fonctionnalités Tenant-Admin | Modifier la langue par défaut |  | v | v    |
| VM | fonctionnalités Tenant-Admin | Désactiver/activer la transcription |  | v | v    |
| VM | fonctionnalités Tenant-Admin | Désactiver/activer la notification d’appel manqué |  | N | v    |
| VM | fonctionnalités Tenant-Admin | Aider Microsoft à améliorer l'aperçu de messagerie vocale    |  | v | v    |
| VM | fonctionnalités Tenant-Admin | Personnaliser le sms pour les utilisateurs activés|  | S/O    | v    |
| VM | fonctionnalités Tenant-Admin | Masquage des vulgarités de transcription|  | v | N    |
| VM | fonctionnalités Tenant-Admin | Stratégie de messagerie vocale    |   | v | v    |
| VM | fonctionnalités Tenant-Admin | Administration du portail web   |  | CY19   | v    |
| VM | fonctionnalités Tenant-Admin | PowerShell   |  | v | v    |
| Messagerie unifiée | Fonctionnalités utilisateur | Indicateur d’attente de message (MWI) sur Skype Entreprise téléphones certifiés   |Peut être fourni par le partenaire téléphonique  | Non | Oui    |
| AA | Fonctionnalités du service | Prise en charge par AA du PBX tiers    |  | N | v    |
| AA | Fonctionnalités du service | Skype Entreprise Server de support   |  | v | v    |
| AA | Fonctionnalités du service | Prise en charge Microsoft Teams|  | v | N    |
| AA | Fonctionnalités du service | Numérotation par nom, entrée DTMF    |  | v | v    |
| AA | Fonctionnalités du service | Numérotation par nom, entrée vocale  |  | v | v    |
| AA | Fonctionnalités du service | Prise en charge multilingue | Détails du langage ici : [Qu’est-ce que les standards automatiques cloud ?](/microsoftteams/what-are-phone-system-auto-attendants) | v | v    |
| AA | Fonctionnalités du service | Transférer vers un opérateur, un CQ ou un utilisateur |  | v | v    |
| AA | Fonctionnalités du service | Transfert vers un numéro RTC en interne (DID RNL)  |  | v | v    |
| AA | Fonctionnalités du service | Transférer vers un numéro RTC en externe  |  | Consultez la section Problèmes connus ci-dessous | v    |
| AA | Fonctionnalités du service | Heures d'ouverture |  | v | v    |
| AA | Fonctionnalités du service | Options de menu | Options de menu IVR  | v | v    |
| AA | Fonctionnalités du service | Affectation d’un numéro PSTN cloud à AA |  | v | N    |
| AA | Fonctionnalités du service | Affectation d’un numéro PSTN local à AA  |  | v | v    |
| AA | Fonctionnalités du service | Sélection d’utilisateurs personnalisés  | Permettre aux appelants d’atteindre la liste personnalisée des utilisateurs de l’organisation| v | v    |
| AA | Fonctionnalités du service | Traitement après les heures d’ouverture et les congés  |  | v | v    |
| AA | Fonctionnalités du service | Message d’accueil personnalisé à l’aide de la synthèse vocale  |  | v | v    |
| AA | Fonctionnalités du service | Numérotation d’extension   | Atteindre un utilisateur en composant son extension  | v   | v    |
| AA | Fonctionnalités du service | Boîte aux lettres permettant aux appelants AA de laisser un message    |  | v   | v    |
| AA | Fonctionnalités du service | Plusieurs affectations de numéros RTC à un AA|  | v | v    |
| AA | fonctionnalités Tenant-Admin | Administration du portail web   |  | v | N    |
| AA | fonctionnalités Tenant-Admin | Cmdlets PowerShell  |  | v | v    |
| Fax| Fonctionnalités du service | Intégration de télécopie|  | N | v    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plan de test suggéré et validation après la migration pour les administrateurs

Pour vérifier que vos utilisateurs ont été migrés vers Messagerie vocale infonuagique, laissez une messagerie vocale à un utilisateur et vérifiez le corps du message dans Outlook. Messagerie vocale infonuagique messages ont un pied de page qui lit :

« Merci d’avoir utilisé la transcription ! Si vous ne voyez pas de transcription ci-dessus, c’est parce que la qualité audio n’était pas assez claire pour transcrire. »

Lorsque vous testez la fonctionnalité de messagerie vocale après la migration de vos utilisateurs, veillez à prendre en compte les scénarios suivants :

- Validez l’accès à la messagerie vocale sur tous les types de points de terminaison de votre organisation, tels que les applications et les téléphones IP.
- Vérifiez avec les exemples d’utilisateurs que les salutations personnalisées configurées sont lues aux appelants.
- Si votre organisation a une exigence légale ou de conformité pour désactiver la transcription pour les utilisateurs, assurez-vous qu’elle est désactivée après la migration. Pour plus d’informations, consultez [Configurer Messagerie vocale infonuagique](/microsoftteams/set-up-phone-system-voicemail).
- Si vous avez déjà configuré Exchange stratégies et règles de machine virtuelle, assurez-vous qu’elles sont efficaces.
- Familiarisez-vous avec les applets de commande PowerShell du service Messagerie vocale infonuagique pour modifier les paramètres utilisateur.  

### <a name="user-experience-impact"></a>Impact de l’expérience utilisateur

Voici une vue d’ensemble de l’expérience de migration de la messagerie vocale de l’utilisateur final.


|Expérience  |Modification de l’expérience utilisateur|
|---------|---------|
|Notification par e-mail | Aucune modification<br>Aucun e-mail n’est envoyé aux utilisateurs les informant de l’activation/migration du compte de messagerie vocale. |
|Accès aux messages précédents | Aucune modification<br>Les utilisateurs ont accès à leurs messages vocaux précédents dans tous les points de terminaison pris en charge. |
|Réception d’une machine virtuelle dans Outlook, applications SFB| Aucune modification<br>Les utilisateurs continuent de recevoir leurs messages vocaux dans tous les points de terminaison pris en charge. |
|Transcription | Améliorée<br>La transcription de machine virtuelle a un taux de précision beaucoup plus élevé et les langues prises en charge que ExchUMO. |
|Paramètre utilisateur | Nouvelle expérience<br>Les utilisateurs peuvent modifier leurs préférences à partir d’un portail de paramètres utilisateur (USP). Les utilisateurs peuvent accéder à leur usP à partir d’un lien hypertexte dans leur messagerie vocale ou du bouton User-Settings sur leur client SFB ; https://aka.ms/vmsettings.
 |Fonctionnalités| Pour plus d’informations, consultez la comparaison des ensembles de fonctionnalités. |
|règles de Outlook pour les messages de machine virtuelle | Aucune modification<br>Les règles créées précédemment s’appliquent aux messages de machine virtuelle après la migration.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>Gestion et approvisionnement des utilisateurs dans la machine virtuelle

Les nouveaux Skype Entreprise utilisateurs sont automatiquement approvisionnés pour la messagerie vocale cloud lors de leur création. Aucune licence ou travail d’administrateur supplémentaire n’est nécessaire pour approvisionner de nouveaux utilisateurs de messagerie vocale. Consultez [Configurer Messagerie vocale infonuagique](/microsoftteams/set-up-phone-system-voicemail) pour en savoir plus sur la gestion des stratégies pour les utilisateurs existants et nouveaux.

### <a name="admin-auto-attendant-management-experience"></a>Administration expérience de gestion du standard automatique

Pour en savoir plus sur les standards automatiques, consultez [Configurer un standard automatique cloud](/microsoftteams/create-a-phone-system-auto-attendant).

### <a name="known-issues"></a>Problèmes connus

#### <a name="greeting-inconsistencies"></a>Incohérences de message d’accueil

L’accès de l’abonné peut continuer à fonctionner pour votre locataire jusqu’à ce que le service soit complètement mis hors service, même après que tous vos utilisateurs ont été migrés vers Messagerie vocale infonuagique. Pour éviter toute confusion de l’utilisateur et une expérience incohérente, désactivez l’accès de l’abonné, car les salutations changent après la migration. Pour ce faire, supprimez le contact EXUM pour chaque ligne d’accès abonné à l’aide `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact`de .

#### <a name="auto-attendant-call-transfer-to-pstn"></a>Transfert d’appel du standard automatique vers PSTN

Pour transférer un appel de standard automatique à un numéro de téléphone RTC externe via Skype Entreprise Server ou un service response group (RGS) sur Skype Entreprise Server, créez un utilisateur local avec le transfert d’appel défini sur le numéro de téléphone RTC ou le numéro de téléphone RGS. L’utilisateur doit être activé et configuré correctement pour Voix Entreprise et une stratégie de voix doit être affectée.

#### <a name="shared-mailbox-is-still-accessible"></a>La boîte aux lettres partagée est toujours accessible

Une boîte aux lettres partagée configurée à l’aide de Exchange UM Online continue de recevoir des messages après la migration vers la machine virtuelle et d’être accessible aux utilisateurs via Outlook. Toutefois, l’accès pour modifier les messages d’accueil de ces boîtes aux lettres ne sera pas disponible une fois migré vers la machine virtuelle. Les clients disposant de boîtes aux lettres partagées qui sont utilisées pour capturer les appelants de standard automatique doivent tirer parti des fonctionnalités de boîte aux lettres partagée des standards automatiques et des files d’attente d’appels une fois publiées (ETA octobre 2019).
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>Bannière « Nom d’utilisateur n’utilise pas Skype Entreprise »

Le service de machine virtuelle est basé sur l’infrastructure Microsoft Teams, et les appels d’un client Skype Entreprise peuvent provoquer l’affichage d’une bannière d’informations sur le client qui indique : « Le nom d’utilisateur n’utilise pas Skype Entreprise. Pour une expérience plus riche, passez à Teams ou démarrez une réunion Skype. »
Veillez à mettre à jour le client Skype Entreprise de vos utilisateurs vers la dernière mise à jour du client C2R pour empêcher l’apparition de cette bannière.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>« Configurer la messagerie vocale » vous amène à OWA

Si vous cliquez sur **Configurer la messagerie vocale** à partir du client, Skype Entreprise Server clients 2015/2013 continueront à accéder à la page du portail Office Web Access (OWA) après la migration vers la machine virtuelle. Tous les paramètres ont été supprimés de l’onglet Messagerie vocale dans OWA et une bannière s’affiche avec un lien de redirection pour diriger les utilisateurs vers le portail des paramètres utilisateur de la machine virtuelle.

#### <a name="changing-greeting-remotely"></a>Modification du message d’accueil à distance

L’accès aux abonnés RTC n’est pas pris en charge dans la machine virtuelle. Pour les utilisateurs qui doivent modifier leur message d’accueil à distance, une option de menu « Modifier votre message d’accueil » a été ajoutée au service IVR de messagerie vocale pour les clients mobiles. Les utilisateurs peuvent appeler ce service en appuyant sur la touche « 1 » sur le pavé de numérotation du client mobile.