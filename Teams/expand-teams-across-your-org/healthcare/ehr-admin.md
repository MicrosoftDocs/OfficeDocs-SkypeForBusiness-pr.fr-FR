---
title: Visites virtuelles avec Teams - Intégration à Epic EHR
author: LanaChin
ms.author: v-lanachin
manager: samanro
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ansantam
description: Découvrez comment intégrer le connecteur Teams DSE pour permettre aux fournisseurs de soins de santé de votre organisation d’effectuer des visites virtuelles avec des patients ou d’autres fournisseurs dans Teams directement à partir du système Epic EHR.
ms.openlocfilehash: e573c30720383554c9bda8467221ff48a1369e0b
ms.sourcegitcommit: 1e8cff687b12348d4ecc538084ab57bbba23b523
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/07/2022
ms.locfileid: "64703600"
---
# <a name="virtual-visits-with-teams---integration-into-epic-ehr"></a>Visites virtuelles avec Teams - Intégration à Epic EHR

Le connecteur de dossiers médicaux électroniques (DSE) Microsoft Teams permet aux cliniciens de lancer facilement une visite ou une consultation de patients virtuels avec un autre fournisseur dans Microsoft Teams directement à partir du système Epic EHR. Basé sur le cloud Microsoft 365, Teams permet une collaboration et une communication simples et sécurisées avec des outils de conversation, de vidéo, de voix et de soins de santé dans un hub unique qui prend en charge la conformité avec HIPAA, la certification HITECH, etc.

La plateforme de communication et de collaboration de Teams permet aux cliniciens de s’occuper facilement de l’encombrement des systèmes fragmentés afin qu’ils puissent se concentrer sur la fourniture des meilleurs soins possibles. Avec le connecteur Teams EHR, vous pouvez :

- Lancez Teams visites virtuelles à partir de votre système Epic EHR avec un flux de travail clinique intégré.
- Permettre aux patients de rejoindre Teams visites virtuelles à partir du portail des patients ou par SMS.
- Prenez en charge d’autres scénarios, notamment les services multi-participants, les visites de groupe et les services d’interpréteur.
- Réécrivez les métadonnées dans le système DSE sur Teams visites virtuelles pour enregistrer lorsque les participants se connectent, se déconnectent et activent l’audit automatique et la conservation des enregistrements.
- Affichez les rapports de données de consommation et les informations de qualité des appels personnalisables pour les visites connectées à la DSE.

Regardez cette vidéo pour obtenir une vue d’ensemble de la gestion des visites virtuelles à partir du portail DSE.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

Cet article explique comment configurer le connecteur Teams EHR pour qu’il s’intègre à la plateforme Epic dans votre organisation de soins de santé. Il vous donne également une vue d’ensemble de l’expérience des visites virtuelles Teams à partir du système Epic EHR.

## <a name="before-you-begin"></a>Avant de commencer

Avant de commencer, il y a quelques choses à faire pour préparer l’intégration.

### <a name="get-familiar-with-the-integration-process"></a>Se familiariser avec le processus d’intégration

Passez en revue les informations suivantes pour comprendre le processus d’intégration global.

:::image type="content" source="media/ehr-connector-epic-flow.png" alt-text="Image résumant les étapes du processus d’intégration global.":::

||||||
|---------|---------|---------|---------|---------|
|**Action** : vous [demandez l’accès à l’application Teams](#request-access-to-the-teams-app). <br> **Résultat** : Nous autorisons votre organisation à effectuer des tests.|**Action** : Nous créons un certificat de clé publique et privée et nous les chargeons dans Epic. <br> **Résultat** : Epic synchronise le certificat de clé publique.|**Action** : Vous effectuez les étapes de configuration dans le portail de configuration du connecteur EHR. <br> **Résultat** : Vous recevez des enregistrements d’IED pour la configuration d’Epic.| **Action** : Vous travaillez avec votre spécialiste technique Epic pour configurer les enregistrements d’IED dans Epic.<br> **Résultat** : Configuration terminée. Prêt à être testé.|**Action** : Vous effectuez les tests dans votre environnement de test.<br> **Résultat** : validation complète des flux et décision de passer à la production.|

### <a name="request-access-to-the-teams-app"></a>Demander l’accès à l’application Teams

Vous devez demander l’accès à l’application Teams.

1. Demande de téléchargement de l’application Teams dans la [Place de marché Epic App Orchard](https://apporchard.epic.com/Gallery?id=6153). Cette opération déclenche une demande d’Epic à l’équipe du connecteur Microsoft EHR.
1. Après avoir fait votre demande, envoyez un e-mail à [TeamsForHealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) avec le nom de votre organisation, l’ID de locataire et l’adresse e-mail de votre contact technique Epic.
1. L’équipe du connecteur Microsoft EHR répond à votre e-mail avec confirmation de l’activation.

### <a name="review-the-epic-microsoft-teams-telehealth-integration-guide"></a>Consultez le guide d’intégration de télésanté Epic-Microsoft Teams

Examinez le [Guide d’intégration de Microsoft Teams télémédecine](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) avec votre spécialiste technique Epic. Assurez-vous que toutes les conditions préalables sont remplies.

## <a name="prerequisites"></a>Conditions préalables

- Un abonnement actif à Microsoft Cloud for Healthcare ou un abonnement à Microsoft Teams’offre autonome du connecteur EHR (appliquée uniquement lors du test dans un environnement de DSE de production).
- Epic version novembre 2018 ou ultérieure.
- Les utilisateurs disposent d’une licence Microsoft 365 ou Office 365 appropriée qui inclut Teams réunions.
- Teams est adopté et utilisé dans votre organisation de soins de santé.
- Vos systèmes répondent à toutes les [exigences en matière de logiciels et de navigateurs](../../hardware-requirements-for-the-teams-app.md) pour Teams.

> [!IMPORTANT]
> Assurez-vous d’effectuer les étapes de pré-intégration et que toutes les conditions préalables sont remplies avant d’aller de l’avant avec l’intégration.

Les étapes d’intégration sont effectuées par les personnes suivantes dans votre organisation :

- **Microsoft 365 administrateur général** : le principal responsable de l’intégration. L’administrateur configure le connecteur, active les SMS (si nécessaire) et ajoute l’analyste client Epic qui approuvera la configuration.
- **Analyste client Epic** : une personne de votre organisation qui a des informations d’identification de connexion à Epic. Ils approuvent les paramètres de configuration entrés par l’administrateur et fournissent les enregistrements de configuration à Epic.

L’administrateur Microsoft 365 et l’analyste client Epic peuvent être la même personne.

## <a name="set-up-the-teams-ehr-connector"></a>Configurer le connecteur DSE Teams

La configuration du connecteur nécessite que vous :

- [Lancer le portail de configuration du connecteur EHR](#launch-the-ehr-connector-configuration-portal)
- [Entrer les informations de configuration](#enter-configuration-information)
- [Activer les notifications SMS (facultatif)](#enable-sms-notifications-optional)
- [Approuver ou afficher la configuration](#approve-or-view-the-configuration)
- [Passer en revue et terminer la configuration](#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>Lancer le portail de configuration du connecteur EHR

Pour commencer, votre administrateur Microsoft 365 lance le [portail de configuration du connecteur EHR](https://ehrconnector.teams.microsoft.com) et se connecte à l’aide de ses informations d’identification Microsoft 365.

Votre administrateur Microsoft 365 peut configurer une seule organisation ou plusieurs organisations pour tester l’intégration. Configurez l’URL de test et de production dans le portail de configuration. Veillez à tester l’intégration à partir de l’environnement de test Epic avant de passer à la production.

> [!NOTE]
> Votre administrateur Microsoft 365 et votre analyste client Epic doivent effectuer les étapes d’intégration dans le portail de configuration. Pour connaître les étapes de configuration d’Epic, contactez le spécialiste technique Epic affecté à votre organisation.

### <a name="enter-configuration-information"></a>Entrer les informations de configuration

Ensuite, pour configurer l’intégration, votre administrateur Microsoft 365 effectue les opérations suivantes :

1. Ajoute une URL de base FHIR (Fast Health Interoperability Resources) à partir de votre spécialiste technique Epic et spécifie l’environnement. Configurez autant d’URL de base FHIR que nécessaire, en fonction des besoins de votre organisation et des environnements que vous souhaitez tester.

    - L’URL de base FHIR est une adresse statique qui correspond au point de terminaison de l’API FHIR de votre serveur. Exemple d’URL est `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

    - Vous pouvez configurer l’intégration pour les environnements de test et de production. Pour la configuration initiale, nous vous encourageons à configurer le connecteur à partir d’un environnement de test avant de passer à la production.

1. Ajoute le nom d’utilisateur de l’analyste client Epic qui approuvera la configuration dans une étape ultérieure.

    :::image type="content" source="media/ehr-connector-epic-configure.png" alt-text="Capture d’écran de la page Configuration, montrant l’approbateur en cours d’ajout." lightbox="media/ehr-connector-epic-configure.png":::

### <a name="enable-sms-notifications-optional"></a>Activer les notifications SMS (facultatif)

> [!NOTE]
> Les notifications SMS sont actuellement disponibles uniquement dans le États-Unis. Nous travaillons à la mise à disposition de cette fonctionnalité dans d’autres régions dans les prochaines versions de Teams et met à jour cet article lorsqu’il sera disponible.

Effectuez cette étape si votre organisation souhaite que Microsoft gère les notifications SMS pour vos patients. Lorsque vous activez les notifications PAR SMS, vos patients reçoivent des messages de confirmation et de rappel pour les visites planifiées.

Pour activer les notifications SMS, votre administrateur Microsoft 365 effectue les opérations suivantes :

1. Dans la page notifications SMS, cochez les deux cases de consentement pour :

    - Autoriser Microsoft à envoyer des notifications SMS aux patients au nom de votre organisation.
    - Reconnaissez que vous allez vous assurer que les participants ont accepté d’envoyer et de recevoir des SMS.
    
    :::image type="content" source="media/ehr-connector-epic-sms-notifications.png" alt-text="Capture d’écran de la page notifications SMS, montrant les cases à cocher de consentement et l’option permettant de générer un numéro de téléphone." lightbox="media/ehr-connector-epic-sms-notifications.png":::

1. Sous **Vos numéros de téléphone**, **sélectionnez Générer un nouveau numéro de téléphone** pour générer un numéro de téléphone pour votre organisation. Cette opération démarre le processus de demande et de génération d’un nouveau numéro de téléphone. Ce processus peut prendre jusqu’à 2 minutes.

    Une fois le numéro de téléphone généré, il s’affiche à l’écran. Ce numéro sera utilisé pour envoyer des confirmations par SMS et des rappels à vos patients. Le nombre a été approvisionné, mais n’est pas encore lié à l’URL de base FHIR. Vous le ferez à l’étape suivante.

    :::image type="content" source="media/ehr-connector-epic-phone-number.png" alt-text="Capture d’écran montrant un exemple de numéro de téléphone généré." lightbox="media/ehr-connector-epic-phone-number.png":::

    Choisissez **Terminé**, puis sélectionnez **Suivant**.

1. Pour lier le numéro de téléphone à une URL de base FHIR, sous **Téléphone numéro** dans la section **configuration SMS**, sélectionnez le numéro. Effectuez cette opération pour chaque URL de base FHIR pour laquelle vous souhaitez activer les notifications SMS.

    :::image type="content" source="media/ehr-connector-epic-link-phone-number.png" alt-text="Capture d’écran montrant comment lier un numéro de téléphone à une URL de base FHIR." lightbox="media/ehr-connector-epic-link-phone-number.png":::

    S’il s’agit de la première fois que vous configurez le connecteur, vous verrez l’URL de base FHIR entrée à l’étape précédente. Le même numéro de téléphone peut être lié à plusieurs URL de base FHIR, ce qui signifie que les patients recevront des notifications PAR SMS du même numéro de téléphone pour différentes organisations et/ou services.

1. Sélectionnez **l’installation sms** en regard de chaque URL de base FHIR pour configurer les types de notifications SMS à envoyer à vos patients.

    :::image type="content" source="media/ehr-connector-epic-sms-setup.png" alt-text="Capture d’écran montrant les paramètres d’installation des SMS." lightbox="media/ehr-connector-epic-sms-setup.png":::

    - **SMS de confirmation** : les notifications sont envoyées aux patients lorsqu’une visite est planifiée, mise à jour ou annulée dans le système DSE.
    - **SMS de rappel** : les notifications sont envoyées aux patients en fonction de l’intervalle de temps que vous spécifiez et de l’heure planifiée de la visite.

    Cliquez sur **Enregistrer**.

1. Sélectionnez **Télécharger certificat** pour charger un certificat de clé publique. Vous devez charger un certificat .cer codé en Base64 (clé publique uniquement) pour chaque environnement.

    Un certificat de clé publique est nécessaire pour recevoir des informations de rendez-vous pour l’envoi de notifications PAR SMS. Le certificat est nécessaire pour vérifier que les informations entrantes proviennent d’une source valide.

    Lorsque le connecteur est utilisé pour envoyer des rappels SMS, le numéro de téléphone du patient est envoyé par Epic dans une charge utile HL7v2 lorsque des rendez-vous sont créés dans Epic. Ces numéros sont stockés pour chaque rendez-vous dans la zone géographique de votre organisation et sont conservés jusqu’à ce que le rendez-vous ait lieu. Pour en savoir plus sur la configuration des messages HL7v2, consultez le [Guide d’intégration de Télésanté Epic-Microsoft Teams](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357).

    Choisissez **Suivant**.

> [!NOTE]
> À tout moment, votre administrateur Microsoft 365 peut mettre à jour n’importe quel paramètre SMS. N’oubliez pas que la modification des paramètres peut entraîner l’arrêt du service SMS. Pour plus d’informations sur l’affichage des rapports SMS, consultez [Teams rapports d’administration du connecteur EHR](ehr-admin-reports.md).

### <a name="approve-or-view-the-configuration"></a>Approuver ou afficher la configuration

L’analyste client Epic de votre organisation qui a été ajouté en tant qu’approbateur lance le [portail de configuration du connecteur EHR](https://ehrconnector.teams.microsoft.com) et se connecte à l’aide de ses informations d’identification Microsoft 365. Une fois la validation réussie, l’approbateur est invité à se connecter à l’aide de ses informations d’identification Epic pour valider l’organisation Epic.

> [!Note]
> Si l’administrateur Microsoft 365 et l’analyste client Epic sont la même personne, vous devez toujours vous connecter à Epic pour valider votre accès. La connexion Epic est utilisée uniquement pour valider votre URL de base FHIR. Microsoft ne stocke pas les informations d’identification ni n’accède aux données DSE avec cette connexion.

:::image type="content" source="media/ehr-connector-epic-login-approve.png" alt-text="Capture d’écran de la page Approuver ou Afficher la configuration, montrant l’option Connexion et approbation." lightbox="media/ehr-connector-epic-login-approve.png":::

Une fois la connexion à Epic réussie, l’analyste client Epic **doit** approuver la configuration. Si la configuration n’est pas correcte, votre administrateur Microsoft 365 peut se connecter au portail de configuration et modifier les paramètres.

:::image type="content" source="media/ehr-connector-epic-approve.png" alt-text="Capture d’écran de la page Approuver ou Afficher la configuration, montrant l’option Approuver." lightbox="media/ehr-connector-epic-approve.png":::

### <a name="review-and-finish-the-configuration"></a>Passer en revue et terminer la configuration

Lorsque les informations de configuration sont approuvées par l'administrateur Epic, les enregistrements d'intégration pour le lancement du patient et du fournisseur vous sont présentés. Les enregistrements d’intégration sont les suivants :

- Dossiers des patients et des fournisseurs
- Enregistrement SMS direct
- Enregistrement de configuration SMS
- Enregistrement de configuration de test d’appareil

L’analyste client Epic doit fournir ces enregistrements à Epic pour terminer la configuration visites virtuelles dans Epic. Pour plus d’informations, consultez le [Guide d’intégration de télésanté Epic-Microsoft Teams](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357).

> [!Note]  
> À tout moment, l’analyste client Microsoft 365 ou Epic peut se connecter au portail de configuration pour afficher les enregistrements d’intégration et modifier la configuration de l’organisation, si nécessaire.

:::image type="content" source="media/ehr-connector-epic-finish.png" alt-text="Capture d’écran de la page Révision et fin, montrant les informations d’intégration." lightbox="media/ehr-connector-epic-finish.png":::

> [!Note]
> L’analyste client Epic doit terminer le processus d’approbation pour chaque URL de base FHIR configurée par l’administrateur Microsoft 365.

## <a name="launch-teams-virtual-visits"></a>Lancer Teams visites virtuelles

Après avoir effectué les étapes du connecteur EHR et la configuration d’Epic, votre organisation est prête à prendre en charge les visites vidéo avec Teams.

### <a name="virtual-visits-prerequisites"></a>Conditions préalables aux visites virtuelles

- Vos systèmes doivent répondre à toutes les [exigences en matière de logiciels et de navigateurs](../../hardware-requirements-for-the-teams-app.md) pour Teams.

- Vous avez terminé la configuration de l’intégration entre l’organisation Epic et votre organisation Microsoft 365.

### <a name="provider-experience"></a>Expérience fournisseur

Les fournisseurs de soins de santé de votre organisation peuvent participer à des visites à l’aide de Teams de leurs applications de fournisseur Epic (Hyperspace, Haiku, Canto). Le bouton **Commencer la visite virtuelle** est incorporé dans le flux du fournisseur.

Principales fonctionnalités de l’expérience fournisseur :

- Les fournisseurs peuvent rejoindre des visites à l’aide de navigateurs pris en charge ou de l’application Teams.

- Les fournisseurs doivent se connecter une seule fois avec leur compte Microsoft 365 lors de leur première visite.

- Après la connexion unique, le fournisseur est directement conduit au rendez-vous virtuel dans Teams. (Le fournisseur doit être connecté à Teams).

- Les fournisseurs peuvent voir les mises à jour en temps réel des participants se connectant et se déconnectant pour un rendez-vous donné. Les fournisseurs peuvent voir quand le patient est connecté à une visite.

  ![Expérience de fournisseur d’une visite avec un patient.](media/ehc-provider-experience-6.png)

> [!NOTE]
> Toutes les informations entrées dans la conversation de réunion nécessaires à la continuité ou à la rétention des dossiers médicaux doivent être téléchargées, copiées et notifiées par le fournisseur de soins de santé. La conversation ne constitue pas un dossier médical légal ou un jeu d’enregistrements désigné. Les messages de la conversation sont stockés en fonction des paramètres créés par l’administrateur Microsoft Teams.

### <a name="patient-experience"></a>Expérience patient

Le connecteur prend en charge les patients qui rejoignent des visites via MyChart web et mobile. Au moment du rendez-vous, les patients peuvent commencer une visite à partir de MyChart à l’aide du bouton **Commencer la visite virtuelle** .

Principales fonctionnalités de l’expérience du patient :

- Les patients peuvent rejoindre des visites à partir de [navigateurs web modernes sur le bureau et mobile sans avoir à installer l’application Teams](../browser-join.md).

- Les patients peuvent rejoindre des visites en un seul clic et aucun autre compte ou connexion n’est requis.

- Les patients ne sont pas tenus de créer un compte Microsoft ou de se connecter pour lancer une visite.

- Les patients sont placés dans une salle d’attente jusqu’à ce que le fournisseur les rejoigne et les admet.

- Les patients peuvent tester leur vidéo et leur microphone dans la salle d’attente avant de rejoindre la visite.

  ![Expérience du patient de la visite.](media/ehc-virtual-visit-5.png)

> [!Note]
> Epic, MyChart, Haiku et Canto sont des marques déposées d'Epic Systems Corporation.

## <a name="get-insight-into-virtual-visits-usage"></a>Obtenir des insights sur l’utilisation des visites virtuelles

Le [rapport d’utilisation des visites virtuelles](../../teams-analytics-and-reports/virtual-visits-usage-report.md) dans le centre d’administration Microsoft Teams donne aux administrateurs une vue d’ensemble de Teams activité Visites virtuelles dans votre organisation. Le rapport présente des analyses détaillées pour les rendez-vous virtuels, notamment Teams réunions intégrées à la DSE effectuées à partir de votre système de DSE.

Vous pouvez afficher des métriques clés telles que le temps d’attente de la salle d’attente et la durée de la visite. Utilisez ces informations pour obtenir des insights sur les tendances d’utilisation afin de vous aider à optimiser les visites virtuelles pour obtenir de meilleurs résultats métier.

### <a name="privacy-and-location-of-data"></a>Confidentialité et emplacement des données

Teams’intégration aux systèmes DSE optimise la quantité de données utilisées et stockées lors des flux d’intégration et de visites virtuelles. La solution respecte les principes et les directives générales de Teams en matière de confidentialité et de gestion des données, décrits dans Confidentialité Teams.

Le connecteur Teams DSE ne stocke ni ne transfère les données personnelles identifiables ni les dossiers de santé des patients ou des fournisseurs de soins de santé à partir du système DSE. Les seules données stockées par le connecteur DMI sont l’ID unique de l’utilisateur DMI (utilisé lors de l’installation d’une réunion Teams).

L’ID unique de l’utilisateur DMI est stocké dans l’une des trois zones géographiques décrites dans [Emplacement de stockage des données client Microsoft 365](/microsoft-365/enterprise/o365-data-locations). Toutes les conversations, enregistrements et autres données partagés dans Teams par les participants à la réunion sont stockés en fonction des stratégies de stockage existantes. Pour en savoir plus sur l’emplacement des données dans Teams, consultez [Emplacement des données dans Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Articles connexes

- [Teams rapport d’utilisation des visites virtuelles](../../teams-analytics-and-reports/virtual-visits-usage-report.md)
- [Teams rapports d’administration du connecteur EHR](ehr-admin-reports.md)
- [Démarrage avec Teams pour les organisations de santé](teams-in-hc.md)
