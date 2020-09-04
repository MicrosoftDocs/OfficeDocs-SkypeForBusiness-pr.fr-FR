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
localization_priority: Normal
description: Microsoft a pu retirer le service de messagerie unifiée Exchange Online (ExchUMO) d’ici le 2020 28 février. Cet article résume les clients concernés et les mesures à prendre pour planifier leur activité.
ms.openlocfilehash: 5d7d9b2e488c61c881395ad00d2675d749e5e30f
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359300"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Prise en charge de la migration en ligne de la messagerie unifiée Exchange

> [!IMPORTANT]
> **Le service de messagerie unifiée dans Exchange Online n’est pas pris en charge depuis le 28 février 2020, heure du Pacifique. Tous les comptes de messagerie vocale ont été migrés vers le service de messagerie vocale Cloud par Microsoft. Tout trafic de standard automatique restant n’est pas surveillé et peut être interrompu à tout moment.**

En référence à l' [annonce](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) le 8 février 2019, Microsoft a pu retirer le service de messagerie unifiée Exchange Online (ExchUMO) du 28 février 2020. Cet article offre un résumé des éléments que les clients concernés doivent connaître et faire pour planifier leur continuité d’entreprise.

ExchUMO est déployé par les clients pour la messagerie vocale, le standard automatique, la file d’attente d’appels et les services d’intégration de télécopie. Microsoft prévoit d’aider les clients à migrer vers des services de système téléphonique qui prennent déjà en charge des milliers de clients sur Skype entreprise Online et Microsoft Teams.

La messagerie vocale est principalement une migration basée sur Microsoft ; l’implication de l’administrateur et/ou l’investissement peuvent être requis pour un sous-ensemble de clients. Le standard automatique est une migration basée sur un administrateur ; vous devrez recréer les arbres de standard automatique ExchUMO existants dans le service Cloud de standard automatique Cloud. Les clients qui utilisent l’une des fonctionnalités ExchUMO avec un PBX tiers ne seront pas migrés vers les services Cloud Skype car ils ne prennent pas en charge les systèmes PBX tiers. Un plan de retraite pour le support technique tiers a été annoncé dans [ce blog](https://techcommunity.microsoft.com/t5/Exchange-Team-Blog/New-date-for-discontinuation-of-support-for-Session-Border/ba-p/607853), et les clients de ce modèle de déploiement peuvent migrer leurs utilisateurs vers l’une des plateformes/services de communications unifiées de Microsoft ou acquérir une solution de standard automatique et/ou de standard vocale pour ces utilisateurs. L’intégration de la télécopie n’est pas prise en charge dans les services en nuage ; les clients devront migrer vers une solution tierce.

## <a name="who-is-affected"></a>Qui est concerné ?

Les clients qui utilisent l’une des fonctionnalités suivantes du service de messagerie unifiée Exchange sont concernés :

- Service de messagerie vocale
- Service de standard automatique
- Service de file d’attente des appels
- Intégration de la télécopie

> [!Note]
> Les clients qui utilisent l’un des serveurs Exchange locaux avec la messagerie unifiée ne sont pas affectés.

En savoir plus sur l’impact de l’expérience utilisateur et de l’administrateur sur l’impact de l' [expérience utilisateur](#user-experience-impact).

## <a name="migration-plan-overview"></a>Vue d’ensemble du plan de migration

Microsoft a identifié divers déploiements de clients qui utilisent des fonctionnalités de ExchUMO et aidera les clients à migrer en fonction du plan suivant.

|Groupe de clients |Chronologie  |Détails  |
|---------|---------|---------|
|Clients prêts à migrer<br><br>Fonctionnalités à migrer :<br><ul><li>Messagerie vocale</ul>   |   Mars — mai 2019  |Exemples :<ul><li>    Clients avec un déploiement et une utilisation de la messagerie vocale simple<li>Les clients qui ont toutes les exigences établies pour que Microsoft exécute la migration<ul>|
|Clients avec conditions préalables<br><br>Fonctionnalités à migrer :<br><ul><li>Messagerie vocale<li>Standard automatique<li>File d’attente des appels</ul> |  Mai — décembre 2019 |Exemples : <br><ul><li>La configuration hybride n’est pas terminée<li>Les numéros RTC hybrides ne sont pas configurés</ul>|
|Les clients qui ont besoin d’une intervention de l’administrateur & investissement client<br><br>Fonctionnalités à migrer :<ul><li>voicemail<li>Standard automatique<li>Files d’attente d’appels<li>Intégration de la télécopie</ul>| Par le 2020 février  | Exemples : <br><ul><li>Le service ExchUMO est utilisé par un PBX tiers<li>Clients ayant des exigences en matière d’accès abonné RTC<li>Clients sur SFB 2010 (non pris en charge)<li>Intégration de la télécopie</ul> |

## <a name="voicemail-migration-guidelines"></a>Instructions de migration de la messagerie vocale

### <a name="get-informed"></a>Être informé

Familiarisez-vous avec l' [annonce de blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) et cet article pour planifier une migration en douceur pour vos utilisateurs. Pour plus d’informations sur les fonctionnalités de messagerie vocale du système téléphonique [, voir vérifier la messagerie vocale et les options de Skype entreprise](https://support.office.com/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) .  

### <a name="establish-a-skype-for-business-hybrid-topology"></a>Établir une topologie hybride Skype entreprise

Si vous ne disposez pas d’une topologie hybride Skype entreprise établie, vous devez effectuer cette opération pour faciliter la migration de vos utilisateurs de la messagerie vocale. Pour plus d’informations, reportez-vous à la rubrique [configure Skype for Business Hybrid](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) .

> [!Note]
> Vous n’avez pas besoin de migrer vos utilisateurs en ligne pour la migration du service de messagerie vocale. Toutefois, pour que les utilisateurs locaux puissent tirer parti du service de messagerie vocale du système téléphonique, une topologie hybride doit être établie.

### <a name="plan-your-auto-attendant-migration"></a>Planification de la migration de votre standard automatique

Les administrateurs peuvent lancer la migration de leurs standards automatiques depuis ExchUMO vers le standard automatique Cloud à tout moment. Pour plus d’informations, reportez-vous à [la rubrique Configurer un standard automatique de Cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) .

Microsoft continue de fournir des fonctionnalités de standard automatique supplémentaires que les clients peuvent envisager de prendre en compte pour leur migration. Les administrateurs doivent évaluer l’ensemble de fonctionnalités et migrer leurs instances de standard automatique en conséquence. Pour une comparaison des listes de fonctionnalités, voir la [matrice de fonctionnalités ExchUMO et Azure Cloud-based services](#exchumo-and-azure-cloud-based-services-feature-matrix).

### <a name="plan-for-your-voicemail-post-migration-validation-and-testing"></a>Planification de la validation et du test post-migration de votre messagerie vocale

La migration de la messagerie vocale est dirigée par Microsoft. Les administrateurs ne doivent rien faire, étant donné que la topologie hybride prérequise est établie. Microsoft effectue la validation requise et les tests afin de s’assurer que la migration de la messagerie vocale des utilisateurs n’est pas interrompue. Les administrateurs sont encouragés à effectuer des tests et des validations sur le même site. Voir le [plan de test suggéré et la validation post-migration pour les administrateurs](#suggested-test-plan-and-post-migration-validation-for-admins) pour un plan de test recommandé.

> [!Note]
> Lync Server 2010 n’est pas pris en charge. Si vous êtes dans un déploiement de serveur 2010, vous devez planifier une mise à niveau du serveur ou envisager de faire migrer vos utilisateurs vers Microsoft Teams.  

### <a name="monitor-the-admin-notification-center"></a>Surveiller le centre de notification d’administration

Surveillez une notification dans le centre de notification d’administration avec des informations supplémentaires et une chronologie concernant la migration de vos utilisateurs. Les notifications sont envoyées au moins 30 jours avant la période de migration.

> [!Note]
> Si vous avez reçu une notification avec la chronologie de la migration de vos utilisateurs et souhaitez reporter votre migration pour une raison stratégique, vous pouvez le faire en contactant le support Microsoft. Vous ne pouvez pas reporter votre migration au-delà de la date de retraite du 28 février 2020. Pour les clients qui peuvent avoir des questions supplémentaires, contactez votre équipe de compte ou le support Microsoft. Les clients qui utilisent déjà Microsoft 365 ou Office 365 peuvent soumettre un cas de support via le centre d’administration Microsoft 365.

### <a name="consider-opting-in-for-a-planned-migration"></a>Envisager d’opter pour une migration planifiée

Vous pouvez opter pour une migration de service de messagerie vocale planifiée vers CVM. Avant d’opter pour le choix, consultez les détails de cet article, en particulier les sections suivantes :

- Étapes de migration (cette section)
- Matrice de fonctionnalité des services Cloud ExchUMO et Azure
- Impact sur l’expérience utilisateur

Lorsque vous choisissez une migration gérée, vous ne recevrez pas de notification de 30 jours avant la migration dans le centre de messages du portail d’administration de Microsoft 365.

Pour vous inscrire à une migration planifiée, envoyez une demande de courrier électronique à partir de l’adresse de messagerie de votre administrateur à [CVM@microsoft.com](mailto:cvm@microsoft.com) avec les informations suivantes :

- Date par défaut (mardis) : les vagues de migration sont exécutées tous les mardis. Veuillez sélectionner une date sur un mardi qui n’est pas au-delà de 12/3/2019.
 
- ID de client : 32 caractères numériques au format 0046728c-688a-4472-a38f-098fec60ac6x. Vous pouvez trouver votre ID de locataire dans le portail d’administration 365 de Microsoft sous Azure AD ou à l’aide de l’applet de commande PowerShell suivante : `Get-CsTenant | Select ObjectId`

Vous recevrez une confirmation par courrier électronique une fois que votre client aura été correctement migré.

## <a name="auto-attendant-migration-guidelines"></a>Instructions de migration du standard automatique

Les administrateurs de l’organisation Microsoft 365 et Office 365 doivent recréer leurs standards automatiques de messagerie unifiée Exchange dans le service de standard automatique Cloud de Microsoft et changer leurs numéros de téléphone locaux avant la date de désinstallation du service UMO Exchange du 28 février 2020. Il s’agit de la règle recommandée pour réussir la migration et le test de nouveaux standards automatiques Cloud. Si vous avez un grand nombre de standards automatiques, vous pouvez utiliser le [standard automatique de messagerie unifiée Exchange pour les scripts de migration de standard](https://github.com/NathanJBennett/ExUMAAMigrationToCloudAA) automatique de Cloud afin de simplifier la migration en bloc des standards automatiques.

### <a name="auto-attendant-setup"></a>Installation du standard automatique

Nous vous conseillons vivement de commencer la configuration de vos nouveaux standards automatiques dès le début pour éviter les problèmes de dernière minute et pour vous familiariser avec les fonctionnalités et l’expérience du service de standard automatique Cloud. Pour les standards automatiques qui nécessitent une ou plusieurs fonctionnalités d’intervalle, vous pouvez créer et tester les standards automatiques lorsque les fonctionnalités d’espace sont disponibles pour préparer le déploiement. Pour plus d’informations sur les fonctionnalités des intervalles, voir l' [annexe](#appendix).

1. Utilisez les applets de commande Exchange UMO pour exporter la configuration des standards automatiques existants à l’aide de la commande [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant).  
2. Utilisez la cmdlet [Export-UMprompt](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/export-umprompt) dans Exchange Online PowerShell pour exporter les fichiers de support de message d’accueil (le cas échéant) et les convertir au format. mp3.
3. Suivez les instructions indiquées dans plan auto- [standards](../../SfbHybrid/hybrid/plan-cloud-auto-attendant.md) and [set up a Cloud auto standard](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) pour créer des standards automatiques à l’aide du centre d’administration Microsoft teams ou de PowerShell.
4. Vérifiez votre message d’accueil si les options de menu sont modifiées.
5. Configurez les transferts vers vos groupes Response Group à l’aide de la solution de contournement « transfert d’appel vers PSTN » dans la section [problèmes connus](#known-issues) de cet article.  
6. Testez les nouveaux standards automatiques en les appelant en interne ou en affectant un numéro de téléphone test.  

### <a name="cutover"></a>Basculement

1. Basculer vos numéros de téléphone des standards automatiques Exchange UMO vers les nouveaux standards automatiques.
2. Déplacez l’URI SIP de l’objet contact vers le compte de ressource.
3. Testez et validez vos standards automatiques à l’aide des numéros de téléphone nouvellement attribués.

## <a name="appendix"></a>Annexe

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matrice de fonctionnalité des services Cloud ExchUMO et Azure

| Service | Niveau de fonctionnalité | Fonctionnalité | Notes  | Virtual VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| Media  | Fonctionnalités de service| Prise en charge d’un PBX tiers    | Inclusion de toutes les fonctionnalités fournies au système PBX tiers comme indicateur (indicateur de message en attente) à l’aide de messages SIP Notify provenant d’Exchange UM Online | N   | v    |
| Media | Fonctionnalités de service  | Prise en charge de Skype entreprise Server   |  | v | v    |
| Media | Fonctionnalités de service | Prise en charge de Microsoft teams|  | v | N    |
| Media | Fonctionnalités de service | Découverte électronique et conservation  | Pour la sécurité et la conformité  | v | v    |
| Media | Fonctionnalités de service | Prise en charge des règles Exchange | Pour la sécurité et la conformité  | v | v    |
| Media | Fonctionnalités utilisateur | Accès commuté RTC  | Accès abonné  | N | v    |
| Media | Fonctionnalités utilisateur | Délégué  | message d’appel manqué  | N | v    |
| Media | Fonctionnalités utilisateur | RTC Outlook Voice Access   | Accès abonné  | N | v    |
| Media | Fonctionnalités utilisateur | Appels entrants à l’aide d’un point de terminaison authentifié | Appel du service de messagerie vocale pour écouter les messages vocaux et modifier les paramètres de messagerie vocale| v | v    |
| Media | Fonctionnalités utilisateur | Paramètre utilisateur permettant de désactiver la messagerie vocale   |  | v | v    |
| Media | Fonctionnalités utilisateur | Paramètre utilisateur permettant de modifier le message d’accueil personnel  |  | v | v    |
| Media | Fonctionnalités utilisateur | Paramètre utilisateur permettant de créer un message d’accueil OOF  |  | v | v    |
| Media | Fonctionnalités utilisateur | Paramètre utilisateur permettant de modifier la langue par défaut  |  | v | v    |
| Media | Fonctionnalités utilisateur | Paramètre utilisateur pour remplacer le message d’accueil par défaut par synthèse vocale  |  | v | N    |
| Media | Fonctionnalités utilisateur | Enregistrer les messages d’accueil personnels (appareil authentifié) |  | v | v    |
| Media | Fonctionnalités utilisateur | Enregistrer les messages d’accueil personnels (PSTN) — émettre au téléphone |  | N | v    |
| Media | Fonctionnalités utilisateur | Paramètre utilisateur permettant de désactiver la transcription |  | N | v    |
| Media | Fonctionnalités utilisateur | Transcription  |  | v | v    |
| Media | Fonctionnalités utilisateur | INDICATEUR (indicateur d’attente des messages) à l’aide de messages SIP Notify |  | N | v    |
| Media | Fonctionnalités utilisateur | Format de fichier audio MP3 dans Outlook    |  | v | v    |
| Media | Fonctionnalités utilisateur | Contrôle de lecture à vitesse variable |  | v | v    |
| Media | Fonctionnalités utilisateur | Transférer une messagerie vocale  | Transférer une messagerie vocale reçue à d’autres utilisateurs | v | v    |
| Media | Fonctionnalités utilisateur | Envoi d’un message vocal à un groupe d’utilisateurs  |Diffusion de messagerie vocale   | N | v   |
| Media | Fonctionnalités utilisateur | Notification de messagerie vocale à l’aide de SMS    | Les utilisateurs peuvent recevoir un SMS lorsqu’ils ont une nouvelle messagerie vocale    | N | v    |
| Media | Fonctionnalités utilisateur | Langues de salutation prises en charge | Détails : https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | v | v    |
| Media | Fonctionnalités utilisateur | Règles de répondeur automatique |  | v | v    |
| Media | Fonctionnalités utilisateur | Émettre un message sur le téléphone (RTC) | M’appeler sur ma cellule pour écouter le message vocal  | N | v    |
| Media | Fonctionnalités utilisateur | Émettre au téléphone (auth)-pour lire un message | M’appeler sur mon appareil authentifié  | v | v    |
| Media | Fonctionnalités utilisateur | Boîte aux lettres partagée entre plusieurs utilisateurs |  | v | v    |
| Media | Fonctionnalités de l’appelant  | Expérience de l’appelant — messagerie vocale protégée | L’appelant peut choisir une option pour marquer un message enregistré comme protégé| N | v    |
| Media | Fonctionnalités de l’appelant  | Expérience de l’appelant — messagerie vocale privée | L’appelant peut choisir une option pour marquer un message enregistré comme privé  | N | v    |
| Media | Fonctionnalités de l’appelant  | Détection de silence   |  | N | v    |
| Media | Client-fonctionnalités d’administration | Messagerie vocale protégée au niveau du serveur    | Client : l’administrateur peut configurer une règle de niveau de service pour marquer la messagerie vocale entrante comme protégée | v | v    |
| Media | Client-fonctionnalités d’administration | Modifier la durée limite d’enregistrement  |     | v | v    |
| Media | Client-fonctionnalités d’administration | Modifier le délai d’expiration de la détection du silence    |  | N/A    | v    |
| Media | Client-fonctionnalités d’administration | Modifier le nombre d’échecs d’entrée | CVM : préprogrammé préprogrammé sur 3 | N | v    |
| Media | Client-fonctionnalités d’administration | Modifier la langue par défaut |  | v | v    |
| Media | Client-fonctionnalités d’administration | Désactiver/activer la transcription |  | v | v    |
| Media | Client-fonctionnalités d’administration | Désactiver/activer la notification d’appel manqué |  | N | v    |
| Media | Client-fonctionnalités d’administration | Aider Microsoft à améliorer l'aperçu de messagerie vocale    |  | v | v    |
| Media | Client-fonctionnalités d’administration | Personnaliser les messages texte pour les utilisateurs activés|  | N/A    | v    |
| Media | Client-fonctionnalités d’administration | Masquage de transcription|  | v | N    |
| Media | Client-fonctionnalités d’administration | Stratégie de messagerie vocale    |   | v | v    |
| Media | Client-fonctionnalités d’administration | Administration du portail Web   |  | CY19   | v    |
| Media | Client-fonctionnalités d’administration | PowerShell   |  | v | v    |
| MESSAGERIE | Fonctionnalités utilisateur | Indicateur de message en attente (indicateur) sur les téléphones certifiés Skype entreprise   |Peut être fourni par un partenaire de téléphone  | Non | Oui    |
| AUTOMATIQUE | Fonctionnalités de service | AA prennent en charge PBX tiers    |  | N | v    |
| AUTOMATIQUE | Fonctionnalités de service | Prise en charge de Skype entreprise Server   |  | v | v    |
| AUTOMATIQUE | Fonctionnalités de service | Prise en charge de Microsoft teams|  | v | N    |
| AUTOMATIQUE | Fonctionnalités de service | Numérotation par nom, entrée DTMF    |  | v | v    |
| AUTOMATIQUE | Fonctionnalités de service | Numérotation par nom, entrée vocale  |  | v | v    |
| AUTOMATIQUE | Fonctionnalités de service | Prise en charge de plusieurs langues | Détails de la langue : https://docs.microsoft.com/microsoftteams/what-are-phone-system-auto-attendants | v | v    |
| AUTOMATIQUE | Fonctionnalités de service | Transférer vers l’opérateur, CQ ou un utilisateur |  | v | v    |
| AUTOMATIQUE | Fonctionnalités de service | Transférer vers le numéro RTC en interne (DID RNL)  |  | v | v    |
| AUTOMATIQUE | Fonctionnalités de service | Transférer vers le numéro RTC en externe  |  | Section problèmes connus (voir ci-dessous) | v    |
| AUTOMATIQUE | Fonctionnalités de service | Heures d'ouverture |  | v | v    |
| AUTOMATIQUE | Fonctionnalités de service | Options de menu | Options de menu de l’IVR  | v | v    |
| AUTOMATIQUE | Fonctionnalités de service | Affectation d’un numéro RTC Cloud à AA |  | v | N    |
| AUTOMATIQUE | Fonctionnalités de service | Affectation d’un numéro RTC sur local à AA  |  | v | v    |
| AUTOMATIQUE | Fonctionnalités de service | Sélection d’utilisateur personnalisée  | Permettre aux appelants d’atteindre la liste personnalisée des utilisateurs de l’Organisation| v | v    |
| AUTOMATIQUE | Fonctionnalités de service | Traitement des heures supplémentaires et des jours fériés  |  | v | v    |
| AUTOMATIQUE | Fonctionnalités de service | Message d’accueil personnalisé utilisant la conversion de texte par synthèse vocale  |  | v | v    |
| AUTOMATIQUE | Fonctionnalités de service | Numérotation d'extension   | Atteindre un utilisateur en composant son poste  | v   | v    |
| AUTOMATIQUE | Fonctionnalités de service | Boîte aux lettres pour les appelants AA devant laisser un message    |  | v   | v    |
| AUTOMATIQUE | Fonctionnalités de service | Plusieurs attributions de numéros RTC à un AA|  | v | v    |
| AUTOMATIQUE | Client-fonctionnalités d’administration | Administration du portail Web   |  | v | N    |
| AUTOMATIQUE | Client-fonctionnalités d’administration | Cmdlets PowerShell  |  | v | v    |
| Fax| Fonctionnalités de service | Intégration de la télécopie|  | N | v    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plan de test suggéré et validation post-migration pour les administrateurs

Pour vérifier que vos utilisateurs ont été migrés vers la messagerie vocale Cloud, laissez une messagerie vocale à un utilisateur et vérifiez le corps du message dans Outlook. Les messages vocaux Cloud ont un pied de page qui indique :

«Merci d’utiliser la transcription ! Si vous ne voyez pas de transcription ci-dessus, cela est dû au fait que la qualité audio n’était pas suffisamment claire pour transcrire.

Lors du test de la fonctionnalité de messagerie vocale après la migration de vos utilisateurs, veillez à prendre en compte les scénarios suivants :

- Valider l’accès à la messagerie vocale pour tous les types de points de terminaison de votre organisation, tels que les applications et les téléphones IP.
- Valider avec des exemples d’utilisateurs que les messages d’accueil personnalisés configurés sont diffusés aux appelants.
- Si votre organisation a besoin de désactiver la transcription pour les utilisateurs, assurez-vous qu’elle est désactivée après la migration. Pour plus d’informations, consultez la rubrique [configurer la messagerie vocale Cloud](/microsoftteams/set-up-phone-system-voicemail).
- Si vous avez déjà configuré les stratégies et les règles de la machine virtuelle Exchange, assurez-vous qu’elles sont efficaces.
- Familiarisez-vous avec les applets de commande PowerShell du service de messagerie vocale Cloud pour modifier les paramètres utilisateur.  

### <a name="user-experience-impact"></a>Impact sur l’expérience utilisateur

Voici une présentation de l’expérience de migration de la messagerie vocale de l’utilisateur final.


|Expérience  |Modification de l’expérience utilisateur|
|---------|---------|
|Notification par courrier électronique | Aucune modification<br>Aucun courrier électronique n’est envoyé aux utilisateurs pour les informer sur l’activation/la migration des comptes de messagerie vocale. |
|Accès aux messages précédents | Aucune modification<br>Les utilisateurs ont accès à leurs messages vocaux précédents dans tous les points de terminaison pris en charge. |
|Réception d’un ordinateur virtuel dans Outlook, applications SFB| Aucune modification<br>Les utilisateurs continuent de recevoir leurs messages vocaux dans tous les points de terminaison pris en charge. |
|Transcription | Avancée<br>La transcription CVM a un taux de précision plus élevé et des langues prises en charge par rapport à ExchUMO. |
|Paramètre utilisateur | Nouvelle expérience<br>Les utilisateurs peuvent modifier leurs préférences à partir d’un portail de paramètres utilisateur (USP). Les utilisateurs peuvent accéder à leur USP à partir d’un lien hypertexte dans leur messagerie vocale ou au bouton paramètres utilisateur sur leur client SFB ; https://aka.ms/vmsettings.
 |Fonctionnalités| Pour plus d’informations, reportez-vous à la comparaison des jeux de fonctionnalités. |
|Règles Outlook pour les messages VM | Aucune modification<br>Les règles créées précédemment s’appliqueront aux messages CVM après la migration.
 |

### <a name="user-management-and-provisioning-in-cvm"></a>Gestion et approvisionnement des utilisateurs dans CVM

Les nouveaux utilisateurs de Skype entreprise seront automatiquement mis en service pour la messagerie vocale Cloud lors de leur création. Aucune licence ou tâche d’administration supplémentaire n’est requise pour mettre en service de nouveaux utilisateurs de messagerie vocale. Consultez la rubrique [configurer la messagerie vocale](/microsoftteams/set-up-phone-system-voicemail) sur le Cloud pour en savoir plus sur la gestion des stratégies pour les utilisateurs existants et nouveaux.

### <a name="admin-auto-attendant-management-experience"></a>Expérience de gestion du standard automatique de l’administrateur

Pour en savoir plus sur les standards automatiques, consultez [la rubrique Configurer un standard automatique Cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant).

### <a name="known-issues"></a>Problèmes connus

#### <a name="greeting-inconsistencies"></a>Incohérences des salutations

L’accès abonné peut continuer à fonctionner pour votre client jusqu’à ce que le service soit complètement retiré, même après la migration de tous vos utilisateurs vers la messagerie vocale Cloud. Pour éviter la confusion des utilisateurs et une expérience incohérente, désactivez l’accès abonné depuis le changement d’accueil après la migration. Pour ce faire, supprimez le contact EXUM pour chaque ligne d’accès abonné à l’aide de `Get-CsExUmContact | ?{$_.IsSubscriberAccess -eq $true} | Remove-CsExUmContact` .

#### <a name="auto-attendant-call-transfer-to-pstn"></a>Transfert d’appel de standard automatique vers PSTN

Pour transférer un appel de standard automatique vers un numéro de téléphone RTC externe via Skype entreprise Server ou un service de groupe de réponse (RGS) sur Skype entreprise Server, créez un utilisateur local dont le transfert d’appel est défini sur le numéro de téléphone RTC ou le numéro de téléphone RGS. L’utilisateur doit être activé et configuré correctement pour voix entreprise et une stratégie de voix est attribuée.

#### <a name="shared-mailbox-is-still-accessible"></a>La boîte aux lettres partagée est toujours accessible

Une boîte aux lettres partagée configurée à l’aide de la messagerie unifiée Exchange Online continue à recevoir des messages après la migration vers CVM et être accessible aux utilisateurs via Outlook. Toutefois, l’accès pour modifier les messages de message d’accueil de ces boîtes aux lettres ne sera pas disponible une fois la migration vers CVM. Les clients disposant de boîtes aux lettres partagées utilisées pour capturer des appels de standard automatique doivent utiliser les fonctionnalités de boîtes aux lettres partagées des standards automatiques et des files d’attente d’appels après leur publication (ETA octobre 2019).
  
#### <a name="username-is-not-using-skype-for-business-banner-displays"></a>Affichages de la bannière « le nom d’utilisateur n’utilise pas Skype entreprise »

Le service CVM est basé sur l’infrastructure de Microsoft teams et les appels à partir d’un client Skype entreprise peuvent entraîner l’affichage d’une bannière d’informations sur le client qui indique : «le nom d’utilisateur n’utilise pas Skype entreprise. Pour une expérience plus riche, passez à teams ou démarrez une réunion Skype. "
Assurez-vous de mettre à jour le client Skype entreprise de vos utilisateurs vers la dernière mise à jour du client C2R pour empêcher l’affichage de cette bannière.
  
#### <a name="set-up-voice-mail-takes-you-to-owa"></a>« Configurer la messagerie vocale » vous permet d’accéder à OWA

En cliquant sur **configurer la messagerie vocale** à partir du client, les clients de Skype entreprise Server 2015/2013 continueront de prendre part à la page du portail Office Web Access (OWA) après la migration vers CVM. Tous les paramètres ont été supprimés de l’onglet messagerie vocale dans OWA et une bannière s’affiche avec un lien de redirection pour prendre les utilisateurs au portail des paramètres utilisateur de CVM.

#### <a name="changing-greeting-remotely"></a>Modification d’un message d’accueil à distance

L’accès abonné PSTN n’est pas pris en charge dans CVM. Pour les utilisateurs qui ont besoin de modifier leur message d’accueil à distance, une option de menu « modifier votre message d’accueil » a été ajoutée au service de messagerie vocale vocale pour les clients mobiles. Les utilisateurs peuvent appeler ce service en appuyant sur la touche « 1 » et en la maintenant enfoncée sur le pavé d’appels du client mobile.
