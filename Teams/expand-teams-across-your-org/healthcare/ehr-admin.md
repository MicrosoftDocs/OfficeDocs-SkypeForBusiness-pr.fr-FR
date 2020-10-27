---
title: Équipes pour les visites virtuelles
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Utiliser Microsoft teams pour configurer votre système de visites virtuelles
ms.openlocfilehash: dcf852486d6a7fbace23bea5fb8610c62bdc7e4f
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766717"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a>Visites virtuelles avec teams-Integration dans le DMI

Le connecteur de l’état de santé électronique de Microsoft Teams (DMI) permet aux médecins de lancer facilement une visite ou une consultation virtuelle du patient auprès d’un autre fournisseur en équipe directement à partir du système DMI. Bâti sur le Cloud Microsoft 365, Microsoft teams permet une collaboration simple et sécurisée et une communication avec les outils de chat, de vidéo, de voix et de santé sur un seul et même concentrateur prenant en charge la conformité à la certification HIPAA, Hi-Tech, etc.

La plateforme de communication et de collaboration d’équipes permet aux médecins de réduire le nombre de systèmes fragmentés de façon à ce qu’ils puissent consacrer du temps à la meilleure prise en charge possible. Le connecteur de l’état de santé électronique de Microsoft Teams (DMI) peut :

- Lancer des visites virtuelles d’équipes à partir de portails du fournisseur et du patient.

- Écrivez de nouveau dans les métadonnées du DMI sur les événements de connexion et de déconnexion pour activer l’audit automatique et la conservation des enregistrements.

- Intégration aux flux de travail de clinicien et de patient tout en leur permettant d’utiliser Microsoft Teams.

## <a name="before-you-begin"></a>Avant de commencer

Pour pouvoir intégrer le connecteur DMI, vous devez vous assurer que vous disposez de la configuration requise suivante :

- Abonnement actif à Microsoft Cloud pour la santé ou un abonnement à l’abonnement au connecteur DMI de Microsoft Teams.

- Les utilisateurs doivent disposer d’une licence Microsoft 365 ou Office 365 appropriée incluant les réunions Microsoft Teams.

- Microsoft teams doit être adopté et utilisé au sein de l’organisation.

- Les organisations doivent avoir la version Epic 2018 ou une version ultérieure.

- Vos systèmes doivent répondre à la [Configuration requise pour les logiciels et les navigateurs](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).

Vous aurez également besoin des informations des personnes suivantes de votre organisation :

- Administrateur Microsoft 365

- Administrateur épique

> [!Note]
> Demandez à votre administrateur épique de fournir le Guide d’intégration de Epic-Microsoft teams Telehealth disponible sur le marché épique.

## <a name="connector-setup"></a>Configuration de connecteur

Pour configurer le connecteur, vous avez besoin des éléments suivants :

- [Lancer le portail de configuration de connecteur DMI](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [Configurer les informations d’organisation du fournisseur](ehr-admin.md#configure-provider-organization-information)
- [Vérifier et approuver la configuration](ehr-admin.md#verify-and-approve-the-configuration)
- [Vérifier et terminer la configuration](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[Lancer le portail de configuration de connecteur DMI](#launch-the-ehr-connector-configuration-portal)

La configuration de votre organisation de santé pour lancer des visites virtuelles à l’aide de Microsoft teams démarre en lançant le portail de configuration de connecteur DMI. Utilisez l’URL de test pour configurer le connecteur pour votre environnement de test épique. Utilisez l’URL de production lorsque vous êtes prêt à activer votre environnement de production épique.
  
- Environnement de test [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)
- Environnement de production [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)

L’administrateur 365 et l’administrateur Epic de votre organisation doivent suivre les informations et les étapes d’intégration du portail de configuration. Pour les étapes de configuration épique, contactez la ressource Epic affectée à votre organisation.

### <a name="configure-provider-organization-information"></a>[Configurer les informations d’organisation du fournisseur](#configure-provider-organization-information)

Cette étape doit être effectuée par l’administrateur Microsoft 365. Pour démarrer le processus de configuration, l’administrateur 365 doit lancer le portail de configuration des connecteurs et se connecter à l’aide des informations d’identification Microsoft.

Pour effectuer cette étape, l’administrateur 365 doit recevoir une URL de base de l’interopérabilité rapide valide de votre administrateur Microsoft 365 et le nom d’utilisateur de l’administrateur Epic qui approuvera la configuration. Pour démarrer le processus de configuration, l’administrateur 365 doit lancer la page Configuration du connecteur et se connecter à l’aide des informations d’identification Microsoft.

- L’URL de base FHIR est une adresse statique correspondant au point de terminaison de l’API FHIR Server. Par exemple, URL [https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST](https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST) .

- Nom de l’approbateur de configuration indique le nom de l’administrateur de système Epic qui sera chargé d’approuver la configuration.

  ![Le nom de l’approbateur de configuration est sélectionné à partir d’une liste dans le connecteur DMI.](../../media/ehc-provider-1.png)

### <a name="verify-and-approve-the-configuration"></a>[Vérifier et approuver la configuration](#verify-and-approve-the-configuration)

L’administrateur épique de votre organisation de soins de santé qui a été ajouté en tant qu’approbateur doit désormais utiliser la même URL de connecteur DMI que l’étape précédente pour se connecter à l’aide de ses informations d’identification Microsoft 365. Après validation réussie, l’approbateur va être invité à se connecter à l’aide de ses informations d’identification Epic pour valider l’organisation Epic.

> [!Note]
> L’administrateur 365 Microsoft et l’administrateur Epic de votre organisation peuvent être la même personne. Dans ce cas, ajoutez votre propre nom d’utilisateur en tant qu’approbateur à la première étape. Vous devrez toujours vous connecter à Epic pour valider votre accès. La connexion épique est utilisée uniquement pour valider votre URL de base FHIR. Microsoft n’enregistre pas les informations d’identification ou accède aux données DMI avec cette connexion.

  ![Vérifiez et approuvez la configuration des informations d’identification.](../../media/ehc-provider-2.png)

Dès qu’un utilisateur se connecte, l’administrateur épique **doit** approuver la configuration. Si la configuration n’est pas correcte, l’administrateur 365 de Microsoft pourra modifier les configurations d’origine en vous connectant au portail du connecteur Microsoft DMI.

![Vérifiez que le connecteur DMI est configuré et qu’il est possible de modifier la configuration.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[Vérifier et terminer la configuration](#review-and-finish-the-configuration)

Lorsque les informations de configuration sont approuvées par l’administrateur épique, vous êtes invité à fournir des enregistrements d’intégration pour le lancement du patient et du fournisseur. Ces enregistrements sont nécessaires pour terminer la configuration de la visite virtuelle dans EPIC. Pour plus d’informations, reportez-vous au Guide d’intégration de Epic-Microsoft teams Telehealth.

> [!Note]  
> À tout moment, l’administrateur Microsoft 365 ou Epic peut se connecter au portail de configuration pour afficher les enregistrements d’intégration et modifier la configuration de l’organisation, si nécessaire.

![Les informations d’intégration sont affichées.](../../media/ehc-final-config-4.png)

## <a name="launch-teams-virtual-visits"></a>Lancer des visites virtuelles dans teams

Après avoir effectué les étapes du connecteur DMI et la configuration épique, votre organisation est prête à prendre en charge les visites vidéo avec Microsoft Teams.

### <a name="virtual-visit-prerequisites"></a>Conditions préalables pour les visites virtuelles

- Vos systèmes doivent répondre à la [Configuration requise pour les logiciels et les navigateurs](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).

- L’organisation du secteur de la santé doit avoir effectué le programme d’installation entre l’organisation Epic et Microsoft 365.

### <a name="provider-experience"></a>Expertise du fournisseur

Les prestataires de services de santé de votre organisation peuvent également rejoindre des visites virtuelles à l’aide de Microsoft teams à partir de leurs applications de fournisseurs de Epic (Hyper-Haiku, Canto). Le bouton **commencer la visite virtuelle** est incorporé dans le flux du fournisseur.

Principales fonctionnalités de l’interface du fournisseur :

- Les fournisseurs peuvent rejoindre des visites virtuelles à l’aide de navigateurs pris en charge ou de l’application Microsoft Teams.

- Les fournisseurs doivent se connecter une seule fois avec leur compte Microsoft 365 pour participer à une visite virtuelle pour la première fois.

- Après la connexion unique, le fournisseur sera directement dirigé vers le rendez-vous virtuel dans Microsoft Teams. (Le fournisseur doit être connecté à Microsoft Teams).

- Le fournisseur peut voir les mises à jour en temps réel des participants se connectent et se déconnectent pour un rendez-vous donné. Le fournisseur peut voir lorsque le patient est connecté à une visite virtuelle.

  ![Expertise d’une visite virtuelle avec le patient](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a>Convivialité du patient

Le connecteur prend en charge les patients qui rejoignent les visites virtuelles via le Web et le mobile de MyChart. Lorsque le rendez-vous est utilisé, les patients peuvent démarrer une visite virtuelle depuis MyChart à l’aide du bouton **commencer la visite virtuelle** .

Principales fonctionnalités de l’interface du patient :

- Les patients peuvent rejoindre des visites virtuelles à partir d’un navigateur Web moderne sur un ordinateur de bureau et sur un appareil mobile sans installation d’applications.

- Les patients peuvent rejoindre des visites virtuelles d’un simple clic et il n’y a pas de compte supplémentaire ou de connexion obligatoire.

- Il n’est pas nécessaire de créer un compte Microsoft ou de vous connecter pour lancer une visite virtuelle.

- Les patients seront placés dans la salle d’attente jusqu’à ce que le prestataire de services de santé rejoigne le rendez-vous et l’autorise à la visite virtuelle.

- Le test de la vidéo et du microphone est disponible dans la salle d’attente avant d’avoir rejoint la visite virtuelle.

  ![Convivialité du patient dans la visite virtuelle](../../media/ehc-virtual-visit-5.png)

> [!Note]
> Epic, MyChart, Haiku et Canto sont des marques commerciales de Epic Systems Corporation.

### <a name="privacy-and-location-of-data"></a>Confidentialité et emplacement des données

L’intégration des équipes aux systèmes DMI optimise le volume de données utilisé et stocké lors de l’intégration et des flux de visites virtuelles. La solution suit les principes et recommandations en matière de gestion de la confidentialité et de la gestion des données de teams dans la vie privée de teams.

Le connecteur DMI de Microsoft Teams ne stocke ni ne transmet de données personnelles identifiables ou des enregistrements médicaux de patients ou de prestataires de services de santé du système DMI. Les seules données stockées par le connecteur DMI sont le numéro unique de l’utilisateur DMI, qui est utilisé lors de la configuration d’une réunion Teams. L’identificateur unique de l’utilisateur DMI est stocké dans l’une des trois régions géographiques décrites dans l’article [où sont stockées les données client Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) . Toutes les discussions, tous les enregistrements et autres données entrées dans teams par les participants à la réunion sont stockés conformément aux stratégies de stockage existantes. Pour en savoir plus sur l’emplacement des données dans Microsoft Teams, voir [emplacements des données dans teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).
