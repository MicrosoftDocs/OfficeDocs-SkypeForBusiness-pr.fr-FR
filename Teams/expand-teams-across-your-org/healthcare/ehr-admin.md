---
title: Teams pour les visites virtuelles
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Utiliser Microsoft Teams pour configurer votre système de visites virtuelles
ms.openlocfilehash: 6753afbabf6bbcb420f9ddf479249a968d33eb2c
ms.sourcegitcommit: 2639da2c9f903a9a82866be9db2b69a705c54200
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50055691"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a>Visites virtuelles avec Teams - Intégration à EHR

Microsoft Teams Electronic Health Record (EHR) Connector permet aux cartésiens de lancer facilement une visite de patient virtuel ou une consultation avec un autre fournisseur dans Teams directement à partir du système EHR. Conçu sur le cloud Microsoft 365, Microsoft Teams permet une collaboration et une communication simples et sécurisées grâce aux outils de conversation, vidéo, voix et soins de santé dans un hub unique qui prend en charge la conformité avec hipAA, la certification HITECH et bien plus encore.
La plateforme de communication et de collaboration de Teams permet aux responsables de réduire facilement l’encombrement des systèmes fragmentés et leur permet de consacrer du temps aux meilleurs soins possibles. Microsoft Teams Electronic Health Record (EHR) Connector peut :
- Lancez les visites virtuelles Teams à partir des portails des fournisseurs et des patients.
- Écrivez de nouveau dans les métadonnées EHR sur les événements de connexion et de déconnexion pour activer l’audit automatique et la conservation d’enregistrement.
- Intégrez-vous aux flux de travail de patient et de patient existants tout en leur permettant d’utiliser Microsoft Teams.

  Regardez la vidéo sur la gestion des visites virtuelles à partir du portail EHR.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a>Avant de commencer

Avant d’intégrer le connecteur EHR, vous devez vous assurer que vous avez les conditions préalables suivantes :

- Accès à l’application Microsoft Teams dans [le marketplace App Marketplace de Android.](https://apporchard.epic.com/Gallery?id=6153)

- Abonnement actif à Microsoft Cloud pour les soins de santé ou abonnement à l’offre autonome Microsoft Teams EHR Connector.

- Les utilisateurs doivent avoir une licence Microsoft 365 ou Office 365 appropriée qui inclut les réunions Microsoft Teams.

- Microsoft Teams doit être adopté et utilisé au sein de l’organisation.

- Les organisations doivent avoir cette version en novembre 2018 ou une version ultérieure.

- Vos systèmes doivent satisfaire toutes les conditions requises pour les [logiciels et les navigateurs.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)

Vous aurez également besoin des informations des personnes suivantes de votre organisation :

- Administrateur Microsoft 365

- Analyste client fidèle

> [!Note]
> Demandez à votre spécialiste technique de l’équipement de Epic-Microsoft le guide d’intégration de la téléhealthe de Teams disponible sur le marketplace Dessinsus.

## <a name="connector-setup"></a>Configuration des connecteurs

La configuration du connecteur nécessite que vous :

- [Lancer le portail de configuration du connecteur EHR](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [Informations de configuration](ehr-admin.md#configuration-information)
- [Approuver ou afficher la configuration](ehr-admin.md#approve-or-view-configuration)
- [Passer en revue et terminer la configuration](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[Lancer le portail de configuration du connecteur EHR](#launch-the-ehr-connector-configuration-portal)

La configuration de votre organisation de santé pour lancer des visites virtuelles avec Microsoft Teams commence par le portail de configuration ehr Connector. Vous configurez une ou plusieurs organisations pour tester l’intégration. Configurez l’URL de test et de production dans le portail de configuration. Testez l’intégration à partir de l’environnement de test DeNs avant de passer à la production.
  
- URL de configuration du connecteur EHR : [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)

L’administrateur Microsoft 365 et l’analyste client Yahoo ! de votre organisation doivent suivre les étapes d’intégration et d’information dans le portail de configuration. Pour plus d’informations sur la configuration du site, contactez la ressource du spécialiste technique Desas qui est affectée à votre organisation.

### <a name="configuration-information"></a>[Informations de configuration](#configuration-information)

Cette étape doit être effectuée par **l’administrateur Microsoft 365.** L’administrateur Microsoft 365 doit lancer le portail de configuration des connecteurs et se connecter avec les informations d’identification Microsoft pour démarrer le processus de configuration.

Pour effectuer cette étape, l’administrateur Microsoft 365 doit recevoir une URL de base Fast Health Interoperability Resources (F URL) valide de votre spécialiste technique Ceci et le nom d’utilisateur de l’analyste client Terminée qui approuvera la configuration. L’administrateur Microsoft 365 doit lancer la page de configuration du connecteur et se connecter avec les informations d’identification Microsoft pour démarrer le processus de configuration.

- L’URL de base FEMBA est une adresse statique correspondant au point de terminaison de l’API FEMBA de votre serveur. Par exemple, l’URL `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` est .

- Le nom de l’approbateur de configuration est le nom de l’analyste clientRobien qui sera responsable de l’approbation de la configuration au cours de l’étape suivante. L’analyste client Densoine est une personne de votre organisation qui a accès à La france.

  ![Le nom de l’approveur de configuration est sélectionné dans une liste du connecteur EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[Approuver ou afficher la configuration](#approve-or-view-configuration)

L’analyste client de votre organisation médicale qui a été ajoutée en tant qu’approbation doit maintenant utiliser la même URL de connecteur EHR que lors de l’étape précédente pour se connecter à l’aide de ses informations d’identification Microsoft 365. Une fois la validation validée, l’approuveur sera invité à se connecter à l’aide de ses informations d’identification Densique pour valider l’organisation.

> [!Note]
> L’administrateur Microsoft 365 et l’analyste client Andyh de votre organisation peuvent être la même personne. Dans ce cas, ajoutez votre propre nom d’utilisateur en tant qu’approver. Vous devrez tout de même vous connectez à Ainsi, pour valider votre accès. La validation de la validation de l’URL de base de votre FEMBA est uniquement utilisée. Microsoft ne stocke pas les informations d’identification ou n’accède pas aux données EHR avec cette connexion.

  ![Vérifiez et approuvez la configuration des informations d’identification.](../../media/approve-view-configuration.png)

Après une bonne inscription au service, l’analyste du client Quiz doit **approuver** la configuration. Si la configuration n’est pas correcte, l’administrateur Microsoft 365 aura la possibilité de modifier les configurations d’origine en se connectant à nouveau au portail de connecteur Ehr Microsoft. 

![Confirmez que le connecteur EHR est configuré et l’option de modification de la configuration.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[Passer en revue et terminer la configuration](#review-and-finish-the-configuration)

Lorsque les informations de configuration sont approuvées par l’administrateur d’Équipe, des enregistrements d’intégration pour le lancement par les patients et les fournisseurs s’offrent à vous. Ces enregistrements sont nécessaires pour effectuer la configuration de la visite virtuelle dans Le Monde. Pour plus d’informations, reportez-vous Epic-Microsoft guide d’intégration de la téléhealthe de Teams.

> [!Note]  
> L’analyste client Microsoft 365 ou Yahoo! peut à tout moment se connecter au portail de configuration pour afficher les enregistrements d’intégration et modifier la configuration de l’organisation, si nécessaire.

![Les informations d’intégration s’affichent.](../../media/finish-configuration.png)

> [!Note]
> Avant cela, le processus d’approbation doit être effectué par l’analyste client Qun lui-même pour chaque URL F URL configurée par l’administrateur Microsoft.

![Les informations de configuration sont approuvées.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a>Lancer des visites virtuelles Teams

Une fois que vous avez terminé les étapes du connecteur EHR et la configuration d’Andy, votre organisation est prête à prendre en charge les visites vidéo avec Microsoft Teams.

### <a name="virtual-visit-prerequisites"></a>Conditions préalables pour une visite virtuelle

- Vos systèmes doivent satisfaire toutes les conditions requises pour les [logiciels et les navigateurs.](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)

- L’organisation de soins de santé doit avoir effectué la configuration entre l’organisation Ci-après et l’organisation Microsoft 365.

### <a name="provider-experience"></a>Expérience du fournisseur

Les fournisseurs de soins de votre organisation peuvent également participer à des visites virtuelles avec Microsoft Teams à partir de leurs applications fournisseurs de service (Hyperspace,Pérku, Canto). Le **bouton Démarrer la visite** virtuelle est incorporé dans le flux du fournisseur.

Principales fonctionnalités de l’expérience du fournisseur :

- Les fournisseurs peuvent participer à des visites virtuelles à l’aide de navigateurs pris en charge ou de l’application Microsoft Teams.

- Les fournisseurs doivent se connecter une seule fois avec leur compte Microsoft 365 lorsqu’ils participent à une visite virtuelle pour la première fois.

- Après la première inscription, le fournisseur sera directement placé sur le rendez-vous virtuel dans Microsoft Teams. (Le fournisseur doit être inscrit à Microsoft Teams).

- Le fournisseur peut voir les mises à jour en temps réel des participants se connecter et se déconnecter pour un rendez-vous donné. Le fournisseur peut voir quand le patient est connecté à une visite virtuelle.

  ![Expérience du fournisseur d’une visite virtuelle avec un patient](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a>Expérience des patients

Le connecteur prend en charge les patients rejoignant des visites virtuelles via MyChart web et mobile. Au moment du rendez-vous, les patients peuvent démarrer une visite virtuelle à partir de MyChart à l’aide du **bouton Commencer la visite** virtuelle.

Principales fonctionnalités de l’expérience du patient :

- Les patients peuvent rejoindre des visites virtuelles à partir de navigateurs web modernes sur un ordinateur de bureau ou un appareil mobile sans installation de l’application.

- Les patients peuvent participer à des visites virtuelles d’un simple clic et il n’est pas nécessaire d’utiliser un autre compte ou aucune autre inscription.

- Les patients n’ont pas besoin de créer un compte Microsoft ou de se connecter pour lancer une visite virtuelle.

- Les patients sont placés dans une salle d’accueil jusqu’à ce que le fournisseur de soins rejoigne le rendez-vous et les admette à la visite virtuelle.

- Test de la vidéo et du microphone est disponible dans la salle d’accueil avant de rejoindre la visite virtuelle.

  ![Expérience patient de la visite virtuelle](../../media/ehc-virtual-visit-5.png)

> [!Note]
> Les productions d’Omkt, de MyChart, de Référence et de Canto sont des marques commerciales de Système d’image.

### <a name="privacy-and-location-of-data"></a>Confidentialité et emplacement des données

L’intégration de Teams aux systèmes EHR optimise la quantité de données utilisées et stockées pendant l’intégration et les flux de visites virtuelles. La solution est adaptée aux principes et directives généraux de confidentialité et de gestion des données de Teams décrits dans la protection des données.

Le connecteur EHR de Microsoft Teams ne stocke ni ne transfère aucune donnée personnelle identifiable ou les dossiers médicaux des patients ou fournisseurs de soins à partir du système EHR. Les seules données stockées par le connecteur EHR sont l’ID unique de l’utilisateur EHR, qui est utilisé lors de l’installation de la réunion Teams. L’ID unique de l’utilisateur EHR est stocké dans l’une des trois régions géographiques décrites dans l’emplacement où sont stockées les données client de votre [client Microsoft 365.](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) Toutes les discussions, enregistrements et autres données entrées dans Teams par les participants à la réunion sont stockés conformément aux stratégies de stockage existantes. Si vous voulez en savoir plus sur l’emplacement des données dans Microsoft Teams, consultez [Emplacement des données dans Teams.](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)
