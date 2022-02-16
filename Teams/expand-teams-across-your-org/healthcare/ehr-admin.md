---
title: Visites virtuelles avec Teams - Intégration à EhRExique
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
description: Découvrez comment intégrer le connecteur Teams EHR pour permettre aux fournisseurs de soins de votre organisation d’effectuer des visites virtuelles auprès de patients ou d’autres fournisseurs dans Teams directement à partir du système EHRh.
ms.openlocfilehash: 3274ed2c566008dd7474accf159540c96c82b865
ms.sourcegitcommit: 5880de47e986854fca873ae75f76a7ecad194dff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2022
ms.locfileid: "62763319"
---
# <a name="virtual-visits-with-teams---integration-into-epic-ehr"></a>Visites virtuelles avec Teams - Intégration à EhRExique

Le connecteur Microsoft Teams dossier médical électronique (EHR) permet aux responsables de lancer facilement la visite d’un patient virtuel ou une consultation avec un autre fournisseur dans Microsoft Teams directement à partir du système ehrshique. Conçu sur le cloud Microsoft 365, Teams permet une collaboration et une communication simples et sécurisées grâce aux outils de conversation, vidéo, voix et soins de santé dans un hub unique qui prend en charge la conformité avec hipAA, la certification HITECH et bien plus encore.

La plateforme de communication et de collaboration d’Teams facilite la réduction de l’encombrement des systèmes fragmentés, de sorte qu’ils peuvent se concentrer sur la fourniture des meilleurs soins possibles. Avec le Teams EHR, vous pouvez :

- Lancez Teams visites virtuelles à partir de votre système EHR d’Quyzh avec un flux de travail clinique intégré.
- Permet aux patients de participer Teams visites virtuelles à partir du portail du patient ou via SMS.
- Prise en charge d’autres scénarios, notamment la participation multiple, les visites de groupe et les services d’interprète.
- Écrivez des métadonnées au système EHR à propos de Teams visites virtuelles pour enregistrer lorsque les participants se connectent, se déconnectent et activent l’audit automatique et la conservation d’enregistrement.
- Afficher des rapports de consommation et des informations personnalisables sur la qualité des appels pour les visites connectées à ehr.

Regardez cette vidéo pour avoir un aperçu de la gestion des visites virtuelles à partir du portail EHR.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

Cet article explique comment configurer et configurer le connecteur Teams EHR pour l’intégrer à la plateforme Android dans votre organisation de soins de santé. Il vous offre également une vue d’ensemble de Teams expérience de visites virtuelles du système EHR d’Quns.

## <a name="before-you-begin"></a>Avant de commencer

Avant de commencer, il y a plusieurs choses à faire pour préparer l’intégration.

### <a name="get-familiar-with-the-integration-process"></a>Se familiariser avec le processus d’intégration

Pour mieux comprendre le processus d’intégration global, examinez les informations suivantes.

:::image type="content" source="media/ehr-connector-epic-flow.png" alt-text="Image résumant les étapes du processus d’intégration global.":::

||||||
|---------|---------|---------|---------|---------|
|**Action** : Vous [demandez l’accès à l Teams appeil de messagerie](#request-access-to-the-teams-app). <br> **Résultat :** Nous autorisez votre organisation à des tests.|**Action** : Nous créons un certificat de clé public et privé et nous les téléchargeons dans Le Monde. <br> **Résultat :** Sync synchronise le certificat de clé publique.|**Action** : vous devez effectuer les étapes de configuration dans le portail de configuration du connecteur EHR. <br> **Résultat :** Vous recevez des enregistrements FS pour la configuration d’Quns.| **Action** : Vous travaillez avec votre spécialiste technique Dessé verso pour configurer les enregistrements FX en aoës.<br> **Résultat :** Configuration terminée. Prêt à l’essai.|**Action :** Vous terminez les tests dans votre environnement de test.<br> **Résultat :** validation complète des flux et décision de passer à la production.|

### <a name="request-access-to-the-teams-app"></a>Demander l’accès à l Teams appeil de messagerie

Vous devez demander l’accès à l’Teams client.

1. Demandez à télécharger l’application Teams dans la place de marché [Android App Marketplace](https://apporchard.epic.com/Gallery?id=6153). Cela déclenche une demande d’Quns à l’équipe du connecteur EHR Microsoft.
1. Après avoir fait votre demande, envoyez un courrier électronique à [TeamsForHealthcare@service.microsoft.com](mailto:teamsforhealthcare@service.microsoft.com) nom de votre organisation, ID de client et l’adresse e-mail de votre contact technique).
1. L’équipe du connecteur EHR Microsoft répondra à votre e-mail avec confirmation de l’enablement.

### <a name="review-the-epic-microsoft-teams-telehealth-integration-guide"></a>Consulter le guide Epic-Microsoft Teams’intégration de la téléhealthe

Examinez le [Guide d’intégration de Microsoft Teams télémédecine](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) avec votre spécialiste technique Epic. Assurez-vous que toutes les conditions préalables sont remplies.

## <a name="prerequisites"></a>Conditions préalables

- Abonnement actif à Microsoft Cloud pour la santé abonnement à une offre autonome de connecteur EHR Microsoft Teams (appliqué uniquement lors des tests dans un environnement EHR de production).
- Version finale de novembre 2018 ou ultérieure.
- Les utilisateurs ont une licence Microsoft 365 ou Office 365 licence appropriée qui inclut Teams réunions.
- Teams est adoptée et utilisé dans votre organisation de soins de santé.
- Vos systèmes répondent à [toutes les exigences de logiciel et de navigateur pour](../../hardware-requirements-for-the-teams-app.md) Teams.

> [!IMPORTANT]
> Veillez à effectuer les étapes de pré-intégration et que toutes les conditions préalables sont remplies avant de passer à l’intégration.

Les étapes d’intégration sont effectuées par les membres suivants de votre organisation :

- **Microsoft 365 administrateur global :** responsable principal de l’intégration. L’administrateur configure le connecteur, active les SMS (le cas nécessaire) et ajoute l’analyste client Qui approuvera la configuration.
- **Analyste client de qualité** : une personne de votre organisation qui dispose d’informations d’identification pour s’y connecter. Ils approuvent les paramètres de configuration entrés par l’administrateur et fournissent les enregistrements de configuration à Quns.

L Microsoft 365 administrateur de projet et l’analyste du client d’équipe peuvent être la même personne.

## <a name="set-up-the-teams-ehr-connector"></a>Configurer le connecteur Teams EHR

La configuration du connecteur nécessite que vous :

- [Lancer le portail de configuration du connecteur EHR](#launch-the-ehr-connector-configuration-portal)
- [Entrer les informations de configuration](#enter-configuration-information)
- [Activer les notifications SMS (facultatif)](#enable-sms-notifications-optional)
- [Approuver ou afficher la configuration](#approve-or-view-the-configuration)
- [Passer en revue et terminer la configuration](#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>Lancer le portail de configuration du connecteur EHR

Pour commencer, votre administrateur Microsoft 365 ouvre le portail de configuration du connecteur [EHR](https://ehrconnector.teams.microsoft.com) et se connecte à l’aide de ses informations Microsoft 365 connexion.

Votre Microsoft 365 peut configurer une ou plusieurs organisations pour tester l’intégration. Configurez l’URL de test et de production dans le portail de configuration. Avant de passer à la production, veillez à tester l’intégration à partir de l’environnement test Test Dulx.

> [!NOTE]
> Votre administrateur Microsoft 365 service et l’analyste du client d’origine doivent suivre les étapes d’intégration dans le portail de configuration. Pour plus d’informations sur la configuration de l’équipe, contactez le spécialiste technique Des Techniciens de votre organisation.

### <a name="enter-configuration-information"></a>Entrer les informations de configuration

Pour configurer ensuite l’intégration, votre administrateur Microsoft 365 de projet doit :

1. Ajoute une URL de base des ressources fast health interoperability (FEMBA) de votre spécialiste technique Sous-site et spécifie l’environnement. Configurez autant d’URL de base FEMBA que nécessaire, selon les besoins de votre organisation et les environnements que vous voulez tester.

    - L’URL de base FEMBA est une adresse statique qui correspond au point de terminaison de l’API FEMBA de votre serveur. Exemple d’URL est `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

    - Vous pouvez configurer l’intégration pour les environnements de test et de production. Pour la configuration initiale, nous vous encourageons à configurer le connecteur à partir d’un environnement de test avant de passer à la production.

1. Ajoute le nom d’utilisateur de l’analyste client Qui approuvera la configuration dans une étape ultérieure.

    :::image type="content" source="media/ehr-connector-epic-configure.png" alt-text="Capture d’écran de la page Configuration, montrant l’approbation en cours d’ajout." lightbox="media/ehr-connector-epic-configure.png":::

### <a name="enable-sms-notifications-optional"></a>Activer les notifications SMS (facultatif)

> [!NOTE]
> Les notifications SMS sont actuellement uniquement disponibles aux États-Unis. Nous travaillons à rendre cette fonctionnalité disponible dans d’autres régions dans les prochaines Teams et mettre à jour cet article lorsqu’elle sera disponible.

Terminez cette étape si votre organisation souhaite que Microsoft gère les notifications SMS pour vos patients. Lorsque vous activez les notifications SMS, vos patients reçoivent des messages de confirmation et de rappel pour les visites programmées.

Pour activer les notifications SMS, votre Microsoft 365 de messagerie doit :

1. Sur la page notifications SMS, sélectionnez les deux boîtes à cocher de consentement pour :

    - Autorisez Microsoft à envoyer des notifications PAR SMS à des patients au nom de votre organisation.
    - Reconnaissez que vous devez vous assurer que les participants ont accepté d’envoyer et de recevoir des SMS.
    
    :::image type="content" source="media/ehr-connector-epic-sms-notifications.png" alt-text="Capture d’écran de la page des notifications SMS, montrant les cases à cocher de consentement et l’option de générer un numéro de téléphone." lightbox="media/ehr-connector-epic-sms-notifications.png":::

1. Sous **Vos numéros de téléphone**, **sélectionnez Générer un nouveau numéro de** téléphone pour générer un numéro de téléphone pour votre organisation. Cette opération lance le processus de demande et de génération d’un nouveau numéro de téléphone. Ce processus peut prendre jusqu’à 2 minutes.

    Une fois le numéro de téléphone généré, il s’affiche à l’écran. Ce numéro sera utilisé pour envoyer des confirmations par SMS et des rappels à vos patients. Le numéro a été mis en service, mais n’est pas encore lié à l’URL de base F URL. Vous devez le faire au cours de l’étape suivante.

    :::image type="content" source="media/ehr-connector-epic-phone-number.png" alt-text="Capture d’écran montrant un exemple du numéro de téléphone généré." lightbox="media/ehr-connector-epic-phone-number.png":::

    **Sélectionnez Terminé**, puis **Suivant**.

1. Pour lier le numéro de téléphone à une URL de base FEMBA, sous Téléphone **numéro** dans la section **configuration SMS**, sélectionnez le numéro. Faites cette étape pour chaque URL de base FEMBA pour laquelle vous voulez activer les notifications SMS.

    :::image type="content" source="media/ehr-connector-epic-link-phone-number.png" alt-text="Capture d’écran montrant comment lier un numéro de téléphone à une URL de base F URL." lightbox="media/ehr-connector-epic-link-phone-number.png":::

    Si c’est la première fois que vous configurez le connecteur, l’URL de base FEMBA qui a été entrée à l’étape précédente s’affichera. Le même numéro de téléphone peut être lié à plusieurs URL de base FEMBA, ce qui signifie que les patients reçoivent des notifications SMS en provenance du même numéro de téléphone pour différentes organisations et/ou services.

1. **Sélectionnez l’installation** de SMS en fonction de chaque URL de base de la fonction FEMBA pour configurer les types de notifications SMS à envoyer à vos patients.

    :::image type="content" source="media/ehr-connector-epic-sms-setup.png" alt-text="Capture d’écran montrant les paramètres de configuration des SMS." lightbox="media/ehr-connector-epic-sms-setup.png":::

    - **SMS de confirmation** : des notifications sont envoyées aux patients lorsqu’une visite est programmée, mise à jour ou annulée dans le système EHR.
    - **SMS de rappel** : des notifications sont envoyées aux patients en fonction de l’intervalle de temps que vous spécifiez et de l’heure prévue de la visite.

    Cliquez sur **Enregistrer**.

1. **Sélectionnez Télécharger certificat** pour télécharger un certificat de clé publique. Vous devez télécharger un certificat .cer .base64 codé (clé publique uniquement) pour chaque environnement.

    Un certificat de clé publique est requis pour recevoir les informations de rendez-vous pour l’envoi de notifications SMS. Le certificat est nécessaire pour vérifier que les informations entrantes viennent d’une source valide.

    Lorsque le connecteur est utilisé pour envoyer des rappels SMS, le numéro de téléphone du patient est envoyé parHienne dans une charge utile HL7v2 lorsque les rendez-vous sont créés dansHique. Ces numéros sont stockés pour chaque rendez-vous dans la géographie de votre organisation et sont conservés jusqu’à ce que le rendez-vous prenne place. Pour plus d’informations sur la configuration des messages HL7v2, voir le Guide d’intégration de Microsoft Teams [télésanté](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357).

    **Sélectionnez Suivant**.

> [!NOTE]
> À tout moment, votre administrateur Microsoft 365 peut mettre à jour les paramètres SMS. N’oubliez pas que la modification des paramètres peut entraîner l’arrêt du service SMS. Pour plus d’informations sur l’affichage des rapports SMS, voir Teams d’administration du connecteur [EHR](ehr-admin-reports.md).

### <a name="approve-or-view-the-configuration"></a>Approuver ou afficher la configuration

L’analyste client yahooux de votre organisation qui a été ajouté comme approveur ouvre le portail de configuration du connecteur [EHR](https://ehrconnector.teams.microsoft.com) et se connecte à l’aide de Microsoft 365 de connexion. Une fois la validation réussie, l’approuveur est invité à se connecter à l’aide de ses informations d’identification d’équipe pour valider l’organisation.

> [!Note]
> Si l’Microsoft 365 de l’entreprise et l’analyste du client Andy sont la même personne, vous devrez tout de même vous connectez à Sous-site pour valider votre accès. La validation de la validation de l’URL de base de votre FEMBA est utilisée uniquement. Microsoft ne stocke pas les informations d’identification ou n’accède pas aux données EHR avec cette connexion.

:::image type="content" source="media/ehr-connector-epic-login-approve.png" alt-text="Capture d’écran de la page Approuver ou Afficher la configuration, montrant l’option Se connecter et approuver." lightbox="media/ehr-connector-epic-login-approve.png":::

Une fois la configuration réussie, l’analyste du client Jens **Doit approuver la** configuration. Si la configuration n’est pas correcte, votre Microsoft 365 peut se connecter au portail de configuration et modifier les paramètres.

:::image type="content" source="media/ehr-connector-epic-approve.png" alt-text="Capture d’écran de la page Approuver ou Afficher la configuration, montrant l’option Approuver." lightbox="media/ehr-connector-epic-approve.png":::

### <a name="review-and-finish-the-configuration"></a>Passer en revue et terminer la configuration

Lorsque les informations de configuration sont approuvées par l'administrateur Epic, les enregistrements d'intégration pour le lancement du patient et du fournisseur vous sont présentés. Les enregistrements d’intégration sont les suivants :

- Dossiers des patients et fournisseurs
- Enregistrement SMS direct
- Enregistrement de configuration SMS
- Enregistrement de configuration de test de l’appareil

L’analyste client Denienne doit fournir ces enregistrements à Ces enregistrements pour terminer la configuration des visites virtuelles en Censo. Pour plus d’informations, voir le [Guide d’intégration Microsoft Teams téléhealthe](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357).

> [!Note]  
> À tout moment, l’analyste Microsoft 365 ou du client Titres d’entreprise peut se connecter au portail de configuration pour afficher les enregistrements d’intégration et modifier la configuration de l’organisation, selon les besoins.

:::image type="content" source="media/ehr-connector-epic-finish.png" alt-text="Capture d’écran de la page Révision et fin, affichant des informations d’intégration." lightbox="media/ehr-connector-epic-finish.png":::

> [!Note]
> L’analyste client Terminée doit effectuer le processus d’approbation pour chaque URL de base F URL configurée par l’Microsoft 365 client.

## <a name="launch-teams-virtual-visits"></a>Lancer Teams visites virtuelles

Une fois que vous avez terminé les étapes du connecteur EHR et que vous avez effectué la configuration Densez, votre organisation est prête à prendre en charge les visites vidéo avec Teams.

### <a name="virtual-visits-prerequisites"></a>Conditions préalables pour les visites virtuelles

- Vos systèmes doivent satisfaire toutes [les exigences logicielles et de navigateur pour](../../hardware-requirements-for-the-teams-app.md) Teams.

- Vous avez effectué la configuration de l’intégration entre l’organisation Desas et votre organisation Microsoft 365 groupe.

### <a name="provider-experience"></a>Expérience fournisseur

Les fournisseurs de soins de votre organisation peuvent participer à des visites à l’aide Teams’applications de leur fournisseur en ligne (Hyperspace,Pérku, Canto). Le bouton **Commencer la visite virtuelle** est incorporé dans le flux du fournisseur.

Principales fonctionnalités de l’expérience fournisseur :

- Les fournisseurs peuvent rejoindre des visites à l’aide de navigateurs pris en charge ou de l Teams appe.

- Les fournisseurs doivent se connecter une seule fois à leur compte Microsoft 365 lorsqu’ils participent à une visite pour la première fois.

- Après la première inscription, le fournisseur est directement placé sur le rendez-vous virtuel dans Teams. (Le fournisseur doit être Teams).

- Les fournisseurs peuvent voir les mises à jour en temps réel des participants se connectant et se déconnectant pour un rendez-vous donné. Les fournisseurs peuvent voir quand le patient est connecté à une visite.

  ![Expérience du fournisseur d’une visite chez un patient.](media/ehc-provider-experience-6.png)

> [!NOTE]
> Toute information entrée dans la conversation de réunion nécessaire à des fins de continuité ou de rétention des dossiers médicaux doit être téléchargée, copiée et notée par le fournisseur de soins de santé. La conversation ne constitue pas un dossier médical ni un jeu de dossiers désigné. Les messages de la conversation sont stockés en fonction des paramètres créés par l’Microsoft Teams conversation.

### <a name="patient-experience"></a>Expérience patient

Le connecteur prend en charge les patients rejoignant des visites via Le web et les appareils mobiles MyChart. Au moment du rendez-vous, les patients peuvent démarrer une visite à partir de MyChart à l’aide du **bouton Commencer la visite** virtuelle.

Principales fonctionnalités de l’expérience du patient :

- Les patients peuvent rejoindre des visites à partir de navigateurs web modernes sur un ordinateur de bureau ou un appareil mobile sans avoir [à installer Teams’application](../mobile-browser-join.md).

- Les patients peuvent rejoindre les visites d’un simple clic sans qu’aucune autre compte ou aucune autre inscription ne soit nécessaire.

- Les patients n’ont pas besoin de créer un compte Microsoft ou de se connecter pour lancer une visite.

- Les patients sont placés dans une salle d’accueil jusqu’à ce que le fournisseur les rejoigne et les admette.

- Les patients peuvent tester leur vidéo et leur microphone dans la salle d’accueil avant de rejoindre la visite.

  ![Expérience des patients de la visite.](media/ehc-virtual-visit-5.png)

> [!Note]
> Epic, MyChart, Haiku et Canto sont des marques déposées d'Epic Systems Corporation.

### <a name="privacy-and-location-of-data"></a>Confidentialité et emplacement des données

Teams’intégration aux systèmes EHR optimise la quantité de données utilisées et stockées pendant les flux d’intégration et de visites virtuelles. La solution respecte les principes et les directives générales de Teams en matière de confidentialité et de gestion des données, décrits dans Confidentialité Teams.

Le connecteur Teams EHR ne stocke ni ne transfère aucune donnée personnelle identifiable ou les dossiers médicaux des patients ou fournisseurs de soins à partir du système EHR. Les seules données stockées par le connecteur DMI sont l’ID unique de l’utilisateur DMI (utilisé lors de l’installation d’une réunion Teams).

L’ID unique de l’utilisateur DMI est stocké dans l’une des trois zones géographiques décrites dans [Emplacement de stockage des données client Microsoft 365](/microsoft-365/enterprise/o365-data-locations). Toutes les discussions, enregistrements et autres données partagées dans Teams par les participants à la réunion sont stockées conformément aux stratégies de stockage existantes. Pour en savoir plus sur l’emplacement des données dans Teams, voir Emplacement des données [dans Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Articles connexes

- [Teams rapports d’administrateur du connecteur EHR](ehr-admin-reports.md)
- [Commencer à travailler avec Teams pour les organisations de soins de santé](teams-in-hc.md)
