---
title: Prise en charge de la migration en ligne de la messagerie unifiée Exchange
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Microsoft retraite le service Exchange Unified Messaging Online (ExchUMO) en février 2020. Cet article récapitule ce que les clients concernés doivent savoir et ce qu’ils doivent faire pour planifier leur continuité d’activité.
ms.openlocfilehash: b9353546012a0cf16f154d330f27f36fd360b5ee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36243893"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Prise en charge de la migration en ligne de la messagerie unifiée Exchange

Dans le rapport de l' [annonce](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) du 8 février 2019, Microsoft retraite le service Exchange Unified Messaging Online (ExchUMO) en février 2020. Cet article présente un résumé des utilisateurs concernés et à faire pour planifier leur continuité d’activité. 
 
ExchUMO est déployé par des clients pour la boîte vocale, le standard automatique, la file d’attente des appels et les services d’intégration de télécopie. Microsoft envisage d’aider les clients à migrer sur des services de système téléphonique qui prennent déjà en charge des milliers de clients sur Skype entreprise Online et Microsoft Teams. 

La boîte vocale est essentiellement une migration pilotée par Microsoft; la participation de l’administrateur et l’investissement seront nécessaires pour un sous-ensemble de clients. Les standards automatiques et les files d’attente d’appels ont une migration pilotée par l’administrateur. les administrateurs ont besoin de recréer les arbres de standard automatique ExchUMO existants dans le service de standard automatique du système téléphonique. Les clients qui utilisent une des fonctionnalités ExchUMO avec un système PBX tiers ne migrent pas vers les services Cloud du système téléphonique, car ces services ne prennent pas en charge les systèmes PBX tiers. Un plan de retraite pour le support technique tiers a été annoncé l’année dernière dans [ce blog](https://blogs.technet.microsoft.com/exchange/2017/07/18/discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging
), et les clients dans ce modèle de déploiement peuvent migrer leurs utilisateurs vers l’une des plates-formes ou services de messagerie unifiée Microsoft ou acquérir un message vocal ou automatique tiers solution de surveillance pour ces utilisateurs. L’intégration de télécopie n’est pas prise en charge par le système téléphonique. les clients devront migrer vers une solution tierce. 

### <a name="who-is-affected"></a>Qui est concerné?

Les clients qui utilisent les fonctionnalités suivantes du service Exchange Unified Messaging Online sont concernés:

- Service de boîte vocale
- Service de standard automatique
- Service de files d’attente d’appels
- Intégration de télécopie

> [!Note]
> Les clients qui utilisent un serveur Exchange local avec la messagerie unifiée ne sont pas concernés. 

En savoir plus sur l’impact sur l’utilisateur et l’administrateur sur l’impact de l’utilisation de l' [utilisateur](#user-experience-impact).

## <a name="migration-plan-overview"></a>Vue d’ensemble du plan de migration

Microsoft a identifié de nombreux déploiements de clients qui utilisent des fonctionnalités de ExchUMO et permettent aux clients de migrer en fonction du plan suivant. 

|Groupe de clients |'  |Détails  |
|---------|---------|---------|
|Clients prêts à migrer<br><br>Fonctionnalités à migrer:<br><ul><li>Messagerie vocale</ul>   |   Mars-2019  |Donnés<ul><li>    Clients ayant une simplicité de déploiement et d’utilisation de la boîte vocale<li>Clients ayant établi toutes les exigences requises par Microsoft pour exécuter la migration<ul>|
|Clients ayant des connaissances préalables<br><br>Fonctionnalités à migrer:<br><ul><li>Messagerie vocale<li>Standard automatique<li>File d’attente d’appels</ul> |  Le 2019 décembre |Donnés <br><ul><li>La configuration hybride n’est pas terminée<li>Les numéros PSTN hybrides ne sont pas configurés</ul>|
|Les clients qui ont besoin d’une implication d’administration & investissement client<br><br>Fonctionnalités à migrer:<ul><li>la boîte vocale<li>Standard automatique<li>Files d’attente d’appels<li>Intégration de télécopie</ul>| Par le 2020 février  | Donnés <br><ul><li>Le service ExchUMO est consommé par un PBX tiers<li>Clients ayant besoin d’avoir accès aux abonnés PSTN<li>Clients sur marketing 2010 (non pris en charge)<li>Intégration de télécopie</ul> |

## <a name="migration-steps"></a>Étapes de migration

1.  **Être informé**
 
    Familiarisez-vous avec l' [annonce de blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) et cet article pour planifier une migration fluide pour vos utilisateurs. Pour plus d’informations sur les fonctionnalités de la boîte vocale du système téléphonique, voir la boîte [vocale Skype entreprise et les options](https://support.office.com/en-us/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) .  
 
2.  **Établissement d’une topologie hybride Skype entreprise**

    Si vous n’avez pas créé de topologie hybride Skype entreprise, vous devez effectuer cette opération pour faciliter la migration de vos utilisateurs de la boîte vocale. Pour plus d’informations, reportez-vous à la rubrique [configuration de Skype entreprise hybride](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) . 

    > [!Note]
    > Vous n’avez pas besoin de migrer vos utilisateurs vers en ligne pour la migration du service de boîte vocale. Toutefois, pour permettre aux utilisateurs locaux d’utiliser le service de messagerie vocale du système téléphonique, une topologie hybride doit être établie.

3. **Planifier la migration de votre standard automatique**
    
    Les administrateurs peuvent commencer à tout moment à migrer leurs standards automatiques de ExchUMO vers le standard automatique Cloud. Pour plus d’informations, voir [configurer un standard automatique Cloud](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) . Microsoft continue de fournir des fonctionnalités de standard automatique supplémentaires dont les clients peuvent envisager d’avoir besoin pour leur migration, les administrateurs doivent évaluer l’ensemble de fonctionnalités et migrer leurs instances de standard automatique en conséquence. Pour comparer les listes de fonctionnalités, voir la [matrice de fonctionnalités des services Cloud ExchUMO et Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

4. **Planifiez la validation et le test post-migration de vos messages vocaux**

    La migration de la boîte vocale est pilotée par Microsoft. Il n’est pas nécessaire d’effectuer une action, car la topologie hybride prérequis est établie. Microsoft effectue les opérations de validation et de test requises pour vérifier que la migration de la messagerie vocale de l’utilisateur n’est pas interrompue. Les administrateurs sont invités à effectuer des tests et à valider sur leur côté. Pour plus d’informations sur les plans de test recommandés [, voir plan de test suggéré et validation après la migration pour les administrateurs](#suggested-test-plan-and-post-migration-validation-for-admins) . 

    > [!Note]
    > Lync Server 2010 n’est pas pris en charge. Dans le cas d’un déploiement 2010 Server, vous devez planifier une mise à niveau du serveur ou envisager la migration de vos utilisateurs vers Microsoft teams ou Skype entreprise online.  

5. **Surveiller le centre de notifications d’administration**

    Recherchez une notification dans le centre de notification d’administration contenant des informations et une chronologie supplémentaires concernant la migration de vos utilisateurs. Les notifications sont envoyées au moins 30 jours avant votre période de migration. 

    > [!Note]
    > Si vous avez reçu une notification avec la chronologie de la migration de vos utilisateurs et voulez différer votre migration pour une raison essentielle pour l’entreprise, vous pouvez le faire en contactant le support Microsoft. Notez que vous ne pouvez pas différer votre migration au-delà de la date de retraite, 2020 février. Pour les clients qui peuvent avoir davantage de questions, contactez l’équipe de votre compte ou le support Microsoft. Les clients qui utilisent déjà Office 365 peuvent proposer un dossier d’assistance via le portail d’administration Office 365. 

6. **Vous pouvez opter pour une migration planifiée.**

    Vous pouvez opter pour une migration de service de boîte vocale planifiée vers CVM. Avant de procéder à la vérification, reportez-vous aux détails de cet article, en particulier aux sections suivantes:

    - Étapes de migration (cette section)
    - Matrice de fonctionnalités des services basés sur le Cloud ExchUMO et Azure
    - Impact de l’utilisation de l’utilisateur

    Lorsque vous choisissez une migration gérée, vous ne recevrez pas de notification de 30 jours avant la migration dans le centre de messages du portail d’administration Microsoft 365.
 
    Pour participer à une migration planifiée, envoyez une demande de courrier électronique à partir de l’adresse de messagerie de l’administrateur à [CVM@microsoft.com](mailto:cvm@microsoft.com) avec les informations suivantes:

    - Date préférée (mardi): les ondulations de migration sont exécutées tous les mardis. Merci de sélectionner une date au-delà de 12/3/2019.
 
    - ID de locataire: numéro de 32 caractères au format 0046728c-688a-4472-a38f-098fec60ac6x. Vous pouvez trouver votre ID de locataire dans le portail d’administration Microsoft 365 sous Azure AD, ou à l’aide de l’applet de commande PowerShell suivante:`Get-CsTenant | Select ObjectId`
 
    Vous recevez un message de confirmation dès que votre client est correctement déplacé. 

## <a name="appendix"></a>A

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matrice de fonctionnalités des services basés sur le Cloud ExchUMO et Azure

| Service | Niveau de fonctionnalité | Fonctionnalité | Notes  | Cloud VM/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| Virtual  | Fonctionnalités de service| Prise en charge du PBX tiers    | Incluant toutes les fonctionnalités proposées au PBX tiers, telles que MWI (indicateur d’attente de messages) avec les messages SIP Notify d’Exchange UM en ligne | N   | O    |
| Virtual | Fonctionnalités de service  | Prise en charge de Skype entreprise Server   |  | Y | Y    |
| Virtual | Fonctionnalités de service | Prise en charge de Microsoft teams|  | O | N    |
| Virtual | Fonctionnalités de service | Découverte électronique et conservation  | Sécurité et conformité  | Y | Y    |
| Virtual | Fonctionnalités de service | Prise en charge des règles Exchange | Sécurité et conformité  | Y | Y    |
| Virtual | Fonctionnalités utilisateur | Accès à la Conférence rendez-vous RTC  | Accès abonné  | N | O    |
| Virtual | Fonctionnalités utilisateur | RTC Outlook Voice Access   | Accès abonné  | N | O    |
| Virtual | Fonctionnalités utilisateur | Appel entrant à l’aide d’un point de terminaison authentifié | Appel du service de boîte vocale pour écouter les messages vocaux et modifier les paramètres de la boîte vocale| Y | Y    |
| Virtual | Fonctionnalités utilisateur | Paramètre d’utilisateur pour désactiver la boîte vocale   |  | Y | Y    |
| Virtual | Fonctionnalités utilisateur | Paramètre d’utilisateur permettant de modifier le message d’accueil personnel  |  | Y | Y    |
| Virtual | Fonctionnalités utilisateur | Paramètre d’utilisation pour créer un message d’accueil du Bureau d’absence  |  | Y | Y    |
| Virtual | Fonctionnalités utilisateur | Paramètre utilisateur permettant de modifier la langue par défaut  |  | Y | Y    |
| Virtual | Fonctionnalités utilisateur | Paramètre de l’utilisateur pour remplacer le message d’accueil par défaut par TTS  |  | O | N    |
| Virtual | Fonctionnalités utilisateur | Enregistrer les messages d’accueil personnels (appareil authentifié) |  | Y | Y    |
| Virtual | Fonctionnalités utilisateur | Enregistrer les messages d’accueil personnels (RTC)-lire sur le téléphone |  | N | O    |
| Virtual | Fonctionnalités utilisateur | Paramètre d’utilisateur pour désactiver la transcription |  | N | O    |
| Virtual | Fonctionnalités utilisateur | Fidélité  |  | Y | Y    |
| Virtual | Fonctionnalités utilisateur | Messagerie vocale visuelle sur tous les points de terminaison   | Avec contrôle utilisateur pour lire, supprimer, indicateur d’attente de messages et activation/désactivation de l’État, sur tous les points de terminaison pris en charge  | Y | Y    |
| Virtual | Fonctionnalités utilisateur | Format de fichier audio MP3 dans Outlook    |  | O | Y    |
| Virtual | Fonctionnalités utilisateur | Contrôle de lecture à vitesse variable |  | O | Y    |
| Virtual | Fonctionnalités utilisateur | Transférer un message vocal  | Transférer un message vocal reçu à d’autres utilisateurs | O | Y    |
| Virtual | Fonctionnalités utilisateur | Envoyer un message vocal à un groupe d’utilisateurs  |Diffusion de la boîte vocale   | N | O   |
| Virtual | Fonctionnalités utilisateur | Notification de la boîte vocale par SMS    | Les utilisateurs peuvent recevoir un SMS s’ils ont un nouveau message vocal    | N | O    |
| Virtual | Fonctionnalités utilisateur | Langues d’accueil prises en charge | Détails ici:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | O | Y    |
| Virtual | Fonctionnalités utilisateur | Règles de répondeur automatique |  | O | Y    |
| Virtual | Fonctionnalités utilisateur | Lecture sur le téléphone (RTC)-pour lire le message | M’appeler sur ma cellule pour écouter le message vocal  | N | O    |
| Virtual | Fonctionnalités utilisateur | Lire sur le téléphone (auth)-pour lire le message | M’appeler sur mon appareil authentifié  | O | Y    |
| Virtual | Fonctionnalités utilisateur | Boîte aux lettres partagée entre plusieurs utilisateurs |  | O | Y    |
| Virtual | Fonctionnalités de l’appelant  | Interface utilisateur: boîte vocale protégée | L’appelant peut choisir une option pour marquer un message enregistré comme protégé| N | O    |
| Virtual | Fonctionnalités de l’appelant  | Interface utilisateur: boîte vocale privée | L’appelant peut choisir une option pour marquer un message enregistré comme privé  | N | O    |
| Virtual | Fonctionnalités de l’appelant  | Détection de silence   |  | N | O    |
| Virtual | Client-fonctionnalités d’administration | Messagerie vocale protégée au niveau du serveur    | Client: un administrateur peut configurer une règle de niveau de service pour marquer la boîte vocale comme protégée | O | Y    |
| Virtual | Client-fonctionnalités d’administration | Changer la durée limite d’enregistrement  |     | O | Y    |
| Virtual | Client-fonctionnalités d’administration | Changer le délai de détection du silence    |  | S/O    | Y    |
| Virtual | Client-fonctionnalités d’administration | Changer le nombre d’échecs d’entrée | CVM: préprogrammé sur 3 | N | O    |
| Virtual | Client-fonctionnalités d’administration | Changer la langue par défaut |  | O | Y    |
| Virtual | Client-fonctionnalités d’administration | Activer/désactiver la transcription |  | Y | Y    |
| Virtual | Client-fonctionnalités d’administration | Activer/désactiver les notifications d’appel manqué |  | N | O    |
| Virtual | Client-fonctionnalités d’administration | Aider Microsoft à améliorer l’aperçu de messagerie vocale    |  | Y | Y    |
| Virtual | Client-fonctionnalités d’administration | Personnaliser un message texte pour les utilisateurs activés|  | S/O    | Y    |
| Virtual | Client-fonctionnalités d’administration | Masquage d’inconvenances de transcription|  | O | N    |
| Virtual | Client-fonctionnalités d’administration | Politique de messagerie vocale    |   | Y | Y    |
| Virtual | Client-fonctionnalités d’administration | Administration du portail Web   |  | CY19   | Y    |
| Virtual | Client-fonctionnalités d’administration | PowerShell   |  | Y | Y    |
| INFORMATISÉ | Fonctionnalités de service | AA support de PBX tiers    |  | N | O    |
| INFORMATISÉ | Fonctionnalités de service | Prise en charge de Skype entreprise Server   |  | Y | Y    |
| INFORMATISÉ | Fonctionnalités de service | Prise en charge de Microsoft teams|  | O | N    |
| INFORMATISÉ | Fonctionnalités de service | Numérotation par nom, entrée DTMF    |  | Y | Y    |
| INFORMATISÉ | Fonctionnalités de service | Numérotation par nom, entrée vocale  |  | Y | Y    |
| INFORMATISÉ | Fonctionnalités de service | Prise en charge de plusieurs langues | Détails de la langue:https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| INFORMATISÉ | Fonctionnalités de service | Transférer vers l’opérateur, CQ ou un utilisateur |  | Y | Y    |
| INFORMATISÉ | Fonctionnalités de service | Transfert vers le numéro RTC en interne (RNL)  |  | Y | Y    |
| INFORMATISÉ | Fonctionnalités de service | Transférer vers le numéro RTC en externe  |  | Q3CY19 | Y    |
| INFORMATISÉ | Fonctionnalités de service | Heures d’ouverture |  | Y | Y    |
| INFORMATISÉ | Fonctionnalités de service | Options de menu | Options de menu IVR  | Y | Y    |
| INFORMATISÉ | Fonctionnalités de service | Attribution d’un numéro PSTN Cloud à AA |  | O | N    |
| INFORMATISÉ | Fonctionnalités de service | Attribution d’un numéro PSTN locaux à AA  |  | Y | Y    |
| INFORMATISÉ | Fonctionnalités de service | Sélection d’utilisateur personnalisée  | Permettre aux appelants de joindre une liste personnalisée d’utilisateurs de l’Organisation| Y | Y    |
| INFORMATISÉ | Fonctionnalités de service | Traitement après heures-heures et jours fériés  |  | Y | Y    |
| INFORMATISÉ | Fonctionnalités de service | Message d’accueil personnalisé utilisant conversion de texte par synthèse vocale  |  | Y | Y    |
| INFORMATISÉ | Fonctionnalités de service | Numéro de téléphone   | Accès à un utilisateur en composant son poste  | CY19   | Y    |
| INFORMATISÉ | Fonctionnalités de service | Boîte aux lettres pour AA pour lequel les appelants doivent laisser un message    |  | CY19   | Y    |
| INFORMATISÉ | Fonctionnalités de service | Attributions de numéros PSTN multiples à un AA|  | Y | Y    |
| INFORMATISÉ | Client-fonctionnalités d’administration | Administration du portail Web   |  | O | N    |
| INFORMATISÉ | Client-fonctionnalités d’administration | Cmdlets PowerShell  |  | Y | Y    |
| DelrinaFax| Fonctionnalités de service | Intégration de télécopie|  | N | O    |

### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plan de test et validation après migration suggérées pour les administrateurs

Pour vérifier que vos utilisateurs ont été déplacés vers la boîte vocale Cloud, laissez une boîte vocale à un utilisateur et vérifiez le corps du message dans Outlook.  Les messages vocaux Cloud contiennent un pied de page qui lit les éléments suivants:

**Merci d’utiliser la transcription. Si vous ne voyez pas de transcription plus haut, c’est parce que la qualité audio n’était pas suffisamment claire pour transcrire.**

Lors du test de la fonctionnalité de messagerie vocale après la migration de vos utilisateurs, assurez-vous de prendre en compte les scénarios suivants:

- Valider l’accès à la messagerie vocale au sein de tous les types de points de terminaison de votre organisation: applications et téléphones IP. 
- Validez avec des exemples d’utilisateurs que les messages d’accueil personnalisés configurés sont lus aux appelants.   
- Si votre organisation a un besoin légal ou de conformité pour désactiver la transcription pour les utilisateurs, assurez-vous qu’elle est désactivée après la migration. Pour plus d’informations, consultez la rubrique [configurer la messagerie vocale Cloud](/microsoftteams/set-up-phone-system-voicemail).
- Si vous avez déjà configuré des stratégies et des règles d’ordinateur virtuel Exchange, vérifiez qu’elles sont efficaces.
- Familiarisez-vous avec les cmdlets PowerShell du service de boîte vocale Cloud pour modifier les paramètres de l’utilisateur.  

### <a name="user-experience-impact"></a>Impact de l’utilisation de l’utilisateur

Vous trouverez ci-dessous une présentation de l’utilisation de la migration de la messagerie vocale de l’utilisateur final.


|Expérimenté  |Modification de l’interface utilisateur|
|---------|---------|
|Notification par courrier électronique | Aucun changement<br>Aucun message électronique n’est envoyé aux utilisateurs pour les informer de la boîte vocale activation/migration de compte. |
|Accès aux messages précédents | Aucun changement<br>Les utilisateurs ont accès à leurs messages vocaux antérieurs dans tous les points de terminaison pris en charge. |
|Réception d’une machine virtuelle dans Outlook, applications marketing| Aucun changement<br>Les utilisateurs continuent à recevoir leurs messages vocaux dans tous les points de terminaison pris en charge. |
|Fidélité | Enrichi<br>CVM transcription a un taux de précision bien plus élevé et des langues prises en charge que ExchUMO. |
|Paramètre d’utilisateur | Nouvelle interface<br>Les utilisateurs sont en mesure de changer leurs préférences à partir d’un portail de configuration utilisateur (USP). Les utilisateurs peuvent accéder à leur USP à partir d’un lien hypertexte dans leurs messages vocaux, ou sur le bouton Paramètres de l’utilisateur sur leur client marketing. https://aka.ms/vmsettings.   
 |Fonctionnalités| Pour plus d’informations, consultez la comparaison de la série de fonctionnalités. |
|Règles Outlook pour les messages VM | Aucun changement<br>Les règles précédemment créées s’appliquent aux messages CVM après la migration.
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>Gestion des utilisateurs et approvisionnement dans CVM 

Les nouveaux utilisateurs Skype entreprise seront automatiquement configurés pour la boîte vocale Cloud lors de leur création. Aucun bureau ou licence d’administration supplémentaire n’est requis pour la mise en service des nouveaux utilisateurs de la boîte vocale. Pour en savoir plus sur la gestion des stratégies destinées aux utilisateurs existants et nouveaux, voir [configurer la messagerie vocale Cloud](/microsoftteams/set-up-phone-system-voicemail) .

#### <a name="admin-auto-attendant-management-experience"></a>Interface de gestion du standard automatique d’administration 

Pour en savoir plus sur les standards automatiques, reportez-vous à [la rubrique Configuration d’un standard automatique Cloud](/MicrosoftTeams/create-a-phone-system-auto-attendant.md). 
