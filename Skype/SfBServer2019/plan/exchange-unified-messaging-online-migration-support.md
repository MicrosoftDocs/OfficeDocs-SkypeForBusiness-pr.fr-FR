---
title: Prise en charge de la migration en ligne de la messagerie unifiée Exchange
ms.author: heidip
author: heidip
manager: serdars
ms.reviewer: waseemh, dstrome, balinger
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Microsoft est le retrait Unified Messaging service Exchange Online (ExchUMO) en février 2020. Cet article résume les éléments affectés clients doivent connaître et pour planifier les leur continuité de l’entreprise.
ms.openlocfilehash: e318e6aac1e4c5ab2b9934fd655dc3112120f36b
ms.sourcegitcommit: 38b501cedfe5fa4ab0126f58926fe2ce4f0cdd0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/09/2019
ms.locfileid: "31740932"
---
# <a name="exchange-unified-messaging-online-migration-support"></a>Prise en charge de la migration en ligne de la messagerie unifiée Exchange  

Référence à l' [annonce](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) sur 8 février 2019, Microsoft est le retrait Unified Messaging service Exchange Online (ExchUMO) en février 2020. Cet article offre un résumé de ce que les clients concernés doit connaître et pour planifier les leur continuité de l’entreprise. 
 
ExchUMO est déployé par les clients pour l’intégration aux services de télécopie, standard automatique et/ou de la messagerie vocale. Microsoft prévoit d’aider ces clients à migrer vers ses services informatiques qui prennent en charge des milliers de clients déjà sur Skype pour Business Online et Microsoft Teams. 

Messagerie vocale est essentiellement une migration pilotée par Microsoft ; implication d’administration et/ou d’investissement peut-être être requis pour un sous-ensemble de clients. Standard automatique est une migration piloté par l’administrateur ; Vous devrez recréer les arborescences de standard automatique de ExchUMO existants dans le service en nuage de standard automatique de nuage. Les clients qui utilisent les fonctionnalités ExchUMO avec un système PBX tiers ne seront pas migrés vers Skype cloud services, car ils ne prennent pas en charge les systèmes PBX tiers. Un plan de retraite pour la prise en charge tierce a été annoncé l’année dernière dans [ce blog](https://blogs.technet.microsoft.com/exchange/2017/07/18/discontinuation-of-support-for-session-border-controllers-in-exchange-online-unified-messaging
)et clients dans ce modèle de déploiement peuvent migrer leurs utilisateurs à un des plateformes/services de Communications unifiées de Microsoft ou acquérir une messagerie vocale tiers et/ou solution de standard automatique pour ces utilisateurs. Intégration de télécopie n’est pas pris en charge dans les services en nuage ; les clients devront migrer vers une solution tierce. 

### <a name="who-is-affected"></a>Qui est concerné ?

Les clients qui utilisent les fonctionnalités suivantes d’Exchange Unified Messaging service en ligne sont concernés :

1. Service de messagerie vocale 
2. Service de standard automatique 
3. Intégration de la télécopie 

> [!Note]
> Les clients qui sont à l’aide de serveur Exchange sur site avec la messagerie unifiée ne sont pas affectés. 

En savoir plus sur l’utilisateur et l’impact de l’expérience d’administration dans [l’impact d’expérience utilisateur](#user-experience-impact).

## <a name="migration-plan-overview"></a>Vue d’ensemble du plan de migration

Microsoft a identifié les différents déploiements de clients qui utilisent les fonctionnalités de ExchUMO et seront être aider les clients à migrer selon le plan suivant. 


|Groupe de clients |Chronologie  |Détails  |
|---------|---------|---------|
|Clients qui sont prêts à migrer<br><br>Fonctionnalités de migration :<br><ul><li>Messagerie vocale</ul>   |   Mars – mai 2019  |Exemples :<ul><li>    Clients avec déploiement simple de la messagerie vocale et d’utilisation<li>Clients qui ont toutes les exigences établies pour Microsoft exécuter la migration<ul>|
|Clients avec les conditions préalables<br><br>Fonctionnalités de migration :<br><ul><li>Messagerie vocale<li>Standard automatique</ul> |  Mai – décembre 2019 |Exemples : <br><ul><li>Configuration hybride n’est pas établie/achevée<li>Les numéros PSTN hybride ne sont pas définies</ul>|
|Clients nécessitant un investissement de client d’administration implication &<br><br>Fonctionnalités de migration :<ul><li>messagerie vocale<li>Standard automatique<li>Intégration de la télécopie</ul>| En février 2020  | Exemples : <br><ul><li>Service ExchUMO est utilisée par 3ème partie PBX<li>Clients avec la configuration requise de l’accès abonné PSTN<li>Clients 2010 SFB (non-pris en charge)<li>Intégration de la télécopie</ul> |

## <a name="migration-steps"></a>Étapes de migration

1.  **Obtenir informé**
 
    Familiarisez-vous avec l' [annonce de blog](https://blogs.technet.microsoft.com/exchange/2019/02/08/retiring-unified-messaging-in-exchange-online/) et de cet article pour planifier une migration transparente pour vos utilisateurs. Pour plus d’informations sur les fonctionnalités de messagerie vocale dans le nuage, consultez la rubrique [Vérifier les Skype pour la messagerie vocale d’entreprise et les options](https://support.office.com/en-us/article/check-skype-for-business-voicemail-and-options-2deea7f8-831f-4e85-a0d4-b34da55945a8) .  
 

2.  **Établir un Skype pour la topologie hybride Business**

    Si vous n’avez pas un Skype pour la topologie hybride Business établie, vous devez faire pour permettre une migration en douceur de vos utilisateurs de messagerie vocale. Pour plus d’informations, voir [Configurer les Skype pour un environnement hybride Business](../../SfbHybrid/hybrid/configure-federation-with-skype-for-business-online.md) . 

    > [!Note]
    > Il est inutile de migrer vos utilisateurs en ligne pour la migration de service de messagerie vocale. Toutefois, pour les utilisateurs locaux d’utiliser le service en nuage de la messagerie vocale, une topologie hybride est doit être établie.

3. **Planifier votre migration standard automatique**
    
    Administrateurs peuvent de démarrer la migration les standards automatiques de ExchUMO vers le standard automatique de nuage à tout moment. Pour plus d’informations, consultez [configurer un standard automatique de système téléphonique](https://docs.microsoft.com/microsoftteams/create-a-phone-system-auto-attendant) . Microsoft prévoit de proposer des fonctionnalités standard automatique supplémentaires clients envisager critiques pour leur migration par 2019 mars. Administrateurs doivent évaluer l’ensemble des fonctionnalités et migrer les instances de standard automatique en conséquence. Pour une comparaison de la liste des fonctionnalités, consultez la [matrice de fonctionnalité de services en nuage ExchUMO et Azure](#exchumo-and-azure-cloud-based-services-feature-matrix).

4. **Planifier votre validation après la migration de messagerie vocale et de test**

    Migration de messagerie vocale est Microsoft piloté par ; Administrateurs ne sont pas tenus à rien, étant donné que la topologie hybride prérequis est établie. Microsoft effectuera la validation requise et le test pour vérifier la migration de messagerie vocale des utilisateurs n’est pas interrompue ; Toutefois, administrateurs sont invités à effectuer le test et la validation de leur côté.  Voir [suggérées plan et validation après la migration pour les administrateurs de test](#suggested-test-plan-and-post-migration-validation-for-admins) pour un plan de test recommandée. 

    > [!Note]
    > Lync Server 2010 n’est pas pris en charge. Si vous êtes dans un déploiement de serveurs 2010, planifier une mise à niveau du serveur ou si vous envisagez de migrer vos utilisateurs à Microsoft Teams ou Skype pour Business Online.  

5. **Surveiller le centre de Notification d’administration**

    Cherchez une notification dans le centre de Notification d’administration avec d’autres détails et chronologie concernant la migration de messagerie vocale de vos utilisateurs. Notifications sont envoyées au moins 30 jours avant la période de migration. 

    > [!Note]
    > Si vous voulez reporter votre migration pour une raison critiques a reçu une notification avec chronologie de migration de vos utilisateurs, vous pouvez le faire à contacter le Support Microsoft. Notez que vous ne pouvez pas différer votre migration au-delà de la date de retraite, février 2020. Pour les clients disposant d’autres questions, contactez votre équipe de compte ou le Support Microsoft. Les clients qui utilisent déjà Office 365 peuvent envoyer une demande de support via le portail d’administration d’Office 365. 

6. **Tenez compte des acceptant à partir de mai 2019**

    Vous pouvez choisir d’une migration de service de messagerie vocale au plus tôt en mai 2019 (si vous n’avez pas reçu une notification de la migration), pour aligner votre migration avec une licence annuité ou un administrateur les congés du personnel, ou pour éviter les périodes critiques. Plus d’informations sur le processus d’abonnement seront mis à jour dans cet article avant de mai 2019.  

## <a name="appendix"></a>Annexe

### <a name="exchumo-and-azure-cloud-based-services-feature-matrix"></a>Matrice des fonctionnalités de services en nuage ExchUMO et Azure 




| Service | Niveau de fonctionnalité | Fonctionnalité | Remarques  | Ordinateur virtuel sur le nuage/AA  | ExUMO |
|---------|-------|--------|----|--------|------|
| ORDINATEUR VIRTUEL  | Fonctionnalités du service| Prise en charge du système PBX tiers-3 rd    | Y compris toutes les fonctionnalités fournies à 3e partie PBX comme indicateur (indicateur en attente des messages) à l’aide de SIP notifier les messages à partir d’Exchange UM Online | N   | O    |
| ORDINATEUR VIRTUEL | Fonctionnalités du service  | Prise en charge Skype pour Business Server   |  | O | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités du service | Prise en charge des équipes de Microsoft|  | O | N    |
| ORDINATEUR VIRTUEL | Fonctionnalités du service | Maintenez la découverte électronique  | Sécurité et conformité  | Y | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités du service | Prise en charge des règles d’Exchange | Sécurité et conformité  | Y | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Accès rendez-vous PSTN  | Accès abonné  | N | O    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | PSTN Outlook Voice Access   | Accès abonné  | N | O    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | À l’aide d’un point de terminaison authentifié par un rendez-vous | Appel du service de messagerie vocale pour écouter les messages vocaux et modifier les paramètres de messagerie vocale| Y | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Paramètre de l’utilisateur pour désactiver la messagerie vocale   |  | Y | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Utilisateur à modifier le message d’accueil personnel  |  | Y | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Utilisateur à créer un message d’absence du bureau  |  | Y | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Paramètre de l’utilisateur de changer la langue par défaut  |  | Y | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Paramètre pour remplacer le message d’accueil par défaut avec TTS utilisateur  |  | O | N    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Enregistrement d’accueil (périphérique authentifié) |  | Y | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Enregistrez le message d’accueil personnel (PSTN) - émettre au téléphone |  | N | O    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Paramètre de l’utilisateur pour désactiver la transcription |  | N | O    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Transcription  |  | Y | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Messagerie vocale visuelle sur tous les systèmes d’extrémité   | Contrôle utilisateur pour lire, supprimer, indicateur de message en attente et état-bascule, tous pris en charge points de terminaison  | Y | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Format de fichier audio MP3 dans Outlook    |  | Y | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Contrôle de lecture de vitesse variable |  | Y | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Transférer un message vocal  | Transférer un message vocal reçu à d’autres utilisateurs | O | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Envoyer un message vocal à un groupe d’utilisateurs  |Diffusion de la messagerie vocale   | N | O   |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Notification de messagerie vocale à l’aide de SMS    | Les utilisateurs peuvent recevoir un SMS lorsqu’ils disposent d’une messagerie vocale    | N | O    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Langues prises en charge de message d’accueil | Détails ici :https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | O | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Règles de répondeur automatique |  | O | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Émettre au téléphone (PSTN) - pour lire des messages | M’appeler sur mon cellule pour écouter le message vocal  | N | O    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Émettre au téléphone (authentification) - pour lire des messages | M’appeler sur mon appareil authentifié  | O | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’utilisateur | Boîte aux lettres partagée entre plusieurs utilisateurs |  | O | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’appelant  | Expérience de l’appelant - messagerie vocale protégée | L’appelant peut choisir une option pour marquer un message enregistré comme protégé| N | O    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’appelant  | Expérience de l’appelant - privée de la messagerie vocale | L’appelant peut choisir une option pour marquer un message enregistré comme étant privé  | N | O    |
| ORDINATEUR VIRTUEL | Fonctionnalités de l’appelant  | Détection du silence   |  | N | O    |
| ORDINATEUR VIRTUEL | Fonctionnalités d’administration des clients | Messagerie vocale protégée au niveau du serveur    | Administrateur du client peut configurer une règle de niveau de service pour marquer les messages vocaux entrant protégé | O | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités d’administration des clients | Limite de temps duration modification d’enregistrement  | CVM dur codée à 5 minutes    | N | O    |
| ORDINATEUR VIRTUEL | Fonctionnalités d’administration des clients | Délai d’expiration de détection de silence modification    |  | N/A    | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités d’administration des clients | Modifier le nombre d’échecs d’entrée | CVM : codés en dur 3 | N | O    |
| ORDINATEUR VIRTUEL | Fonctionnalités d’administration des clients | Modifier la langue par défaut |  | O | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités d’administration des clients | Activer/désactiver transcription |  | O | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités d’administration des clients | Activer/désactiver les appels manqués |  | N | O    |
| ORDINATEUR VIRTUEL | Fonctionnalités d’administration des clients | Améliorer Microsoft Aperçu de messagerie vocale    |  | Y | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités d’administration des clients | Personnaliser le message de texte pour les utilisateurs activés|  | N/A    | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités d’administration des clients | Masquage de transcription gratuites|  | O | N    |
| ORDINATEUR VIRTUEL | Fonctionnalités d’administration des clients | Stratégie de messagerie vocale    |   | Y | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités d’administration des clients | Administration du portail Web   |  | CY19   | Y    |
| ORDINATEUR VIRTUEL | Fonctionnalités d’administration des clients | PowerShell   |  | Y | Y    |
| AA | Fonctionnalités du service | Prise en charge CA-3 rd tiers PBX    |  | N | O    |
| AA | Fonctionnalités du service | Prise en charge Skype pour Business Server   |  | Y | Y    |
| AA | Fonctionnalités du service | Prise en charge des équipes de Microsoft|  | O | N    |
| AA | Fonctionnalités du service | Composer un nom, entrée DTMF    |  | Y | Y    |
| AA | Fonctionnalités du service | Composer un nom, la saisie vocale  |  | Y | Y    |
| AA | Fonctionnalités du service | Prise en charge multilingue | Détails langue ici :https://docs.microsoft.com/en-us/microsoftteams/what-are-phone-system-auto-attendants | Y | Y    |
| AA | Fonctionnalités du service | Transférer vers un opérateur, CQ ou un utilisateur |  | Y | Y    |
| AA | Fonctionnalités du service | Transférer vers un numéro RTC en interne (RNL a)  |  | Y | Y    |
| AA | Fonctionnalités du service | Transférer vers un numéro RTC en externe  |  | Q2CY19 | Y    |
| AA | Fonctionnalités du service | Heures d’ouverture |  | Y | Y    |
| AA | Fonctionnalités du service | Options de menu | Options de menu de réponse vocale interactive  | Y | Y    |
| AA | Fonctionnalités du service | Affectation d’un numéro RTC en nuage à AA |  | O | N    |
| AA | Fonctionnalités du service | Affectation d’un numéro PSTN sur prem à AA  |  | Y | Y    |
| AA | Fonctionnalités du service | Sélection de l’utilisateur personnalisée  | Permettant aux appelants de joindre une liste personnalisée d’utilisateurs de l’organisation| Y | Y    |
| AA | Fonctionnalités du service | En continu et les jours fériés de traitement  |  | Y | Y    |
| AA | Fonctionnalités du service | Message d’accueil personnalisé à l’aide de texte par synthèse vocale  |  | Y | Y    |
| AA | Fonctionnalités du service | Numérotation d’extension   | Atteindre un utilisateur par numérotation leur extension  | CY19   | Y    |
| AA | Fonctionnalités du service | Boîte aux lettres pour les appelants AA à laisser un message    |  | CY19   | Y    |
| AA | Fonctionnalités du service | Affectation des numéros RTC plusieurs à un standard automatique|  | Y | Y    |
| AA | Fonctionnalités d’administration des clients | Administration du portail Web   |  | O | N    |
| AA | Fonctionnalités d’administration des clients | Applets de commande PowerShell  |  | Y | Y    |
| Télécopie| Fonctionnalités du service | Intégration de la télécopie|  | N | O    |



### <a name="suggested-test-plan-and-post-migration-validation-for-admins"></a>Plan de test suggérées et validation après la migration pour les administrateurs

Lors du test des fonctionnalités de messagerie vocale, une fois que vos utilisateurs ont été migrés, veillez à prendre en compte les scénarios suivants :

- Valider l’accès de la messagerie vocale pour tous les types de point de terminaison dans votre organisation : des téléphones IP et les applications. 
- Valider les utilisateurs qui le message d’accueil personnalisé configuré est diffusé aux appelants.   
- Si votre organisation a besoin de désactiver la transcription pour les utilisateurs juridiques ou de conformité, assurez-vous qu’il est désactivé après la migration. Pour plus d’informations, voir [configuration de la messagerie vocale dans le nuage](/microsoftteams/set-up-phone-system-voicemail).
- Si vous avez précédemment configuré les règles et stratégies de l’ordinateur virtuel Exchange, assurez-vous qu’ils sont efficaces.
- Familiarisez-vous avec les applets de commande PowerShell de service de la messagerie vocale dans le nuage pour modifier les paramètres utilisateur.  


### <a name="user-experience-impact"></a>Impact sur l’expérience utilisateur

Voici une vue d’ensemble de l’expérience de la migration utilisateur final de la messagerie vocale.


|Expérience  |Modifier l’utilisateur|
|---------|---------|
|Notification par courrier électronique | Aucun changement<br>Aucun courrier électronique n’est envoyé aux utilisateurs pour les informer sur activation/migration des comptes de messagerie vocale. |
|Accès aux messages précédents | Aucun changement<br>Les utilisateurs auront accès à leurs messages vocaux précédente dans tous les points de terminaison pris en charge. |
|Ordinateur virtuel de réception dans outlook, SFB applications| Aucun changement<br>Les utilisateurs continueront à recevoir leurs messages de messagerie vocale dans tous les points de terminaison pris en charge. |
|Transcription | Amélioré<br>Transcription CVM a un taux de précision beaucoup plus élevé et les langues prises en charge que ExchUMO. |
|Paramètre de l’utilisateur | Nouvelle expérience<br>Les utilisateurs pourront modifier leurs préférences d’un portail de paramètre utilisateur (USP). Les utilisateurs peuvent accéder à leur USP à partir d’un lien hypertexte dans leur messagerie électronique de la messagerie vocale ou sur le bouton Paramètres de l’utilisateur sur leur client SFB ; https://aka.ms/vmsettings.   
 |Fonctionnalités| Reportez-vous à la comparaison des fonctionnalités pour plus d’informations. |
|Règles Outlook pour les messages de l’ordinateur virtuel | Aucun changement<br>Précédemment créé des règles seront appliqueront aux messages CVM après la migration.
 |

#### <a name="user-management-and-provisioning-in-cvm"></a>Gestion des utilisateurs et le provisionnement dans CVM 

Skype pour les nouveaux utilisateurs est automatiquement mis en service pour la messagerie vocale dans service CVM lors de la création. Aucun travail d’administration supplémentaire ou une licence n’est nécessaire pour mettre en service les nouveaux utilisateurs pour la messagerie vocale. Voir [configuration de la messagerie vocale dans le nuage](/microsoftteams/set-up-phone-system-voicemail) pour en savoir plus sur la gestion des stratégies pour les utilisateurs nouveaux et existants.

#### <a name="admin-auto-attendant-management-experience"></a>Expérience de gestion de standard automatique de Admin 

Voir la rubrique [configurer un standard automatique de système téléphonique](/MicrosoftTeams/create-a-phone-system-auto-attendant.md) pour en savoir plus sur la configuration et la gestion des standards automatiques. 
