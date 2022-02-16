---
title: Visites virtuelles avec Teams - Intégration à l’intégration à l’intégration EHR
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
description: Découvrez comment intégrer le connecteur Teams EHR pour permettre aux fournisseurs de soins de votre organisation d’effectuer des visites virtuelles avec des patients ou d’autres fournisseurs dans Teams directement à partir du système d’intégration EHR.
ms.openlocfilehash: e7d104e4541462c94ddb95805ae7ec2a8619bf5b
ms.sourcegitcommit: 5880de47e986854fca873ae75f76a7ecad194dff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2022
ms.locfileid: "62763698"
---
# <a name="virtual-visits-with-teams---integration-into-cerner-ehr"></a>Visites virtuelles avec Teams - Intégration à l’intégration à l’intégration EHR

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Le connecteur Microsoft Teams dossier médical électronique (EHR) permet aux responsables de lancer facilement la visite d’un patient virtuel ou de consulter un autre fournisseur dans Microsoft Teams directement à partir du système d’électronique d’enregistrement électronique (EHR). Conçu sur le cloud Microsoft 365, Teams permet une collaboration et une communication simples et sécurisées grâce aux outils de conversation, vidéo, voix et soins de santé dans un hub unique qui prend en charge la conformité avec hipAA, la certification HITECH et bien plus encore.

La plateforme de communication et de collaboration d’Teams facilite la réduction de l’encombrement des systèmes fragmentés, de sorte qu’ils peuvent se concentrer sur la fourniture des meilleurs soins possibles. Avec le Teams EHR, vous pouvez :

- Effectuez Teams visites virtuelles à partir de votre système d’intégration EHR avec un flux de travail clinique intégré.
- Permet aux patients de participer Teams visites virtuelles à partir de notifications par courrier électronique ou SMS.
- Afficher des rapports de consommation et des informations personnalisables sur la qualité des appels pour les visites connectées à ehr.

Cet article explique comment configurer et configurer le connecteur Teams EHR pour l’intégrer à la plateforme Cerner. Il vous offre également une vue d’ensemble de l Teams expérience de visites virtuelles à partir du système d’environnement de gestion des biens et des environnements virtuels.

## <a name="before-you-begin"></a>Avant de commencer

> [!NOTE]
> Veillez à parler à votre représentant cerner et à consulter votre guide d’intégration d’Cerner avant d’activer l’intégration.

### <a name="prerequisites"></a>Conditions préalables

Avant d’intégrer le connecteur Teams EHR dans votre organisation de soins de santé, vous devez avoir les connecteurs suivants :

- Abonnement actif à Microsoft Teams offre autonome de connecteur EHR (appliquée uniquement lors du test dans un environnement EHR de production).
- Les utilisateurs ont une licence Microsoft 365 ou Office 365 licence appropriée qui inclut Teams réunions.
- Teams est adoptée et utilisé dans votre organisation de soins de santé.
- Vos systèmes répondent à [toutes les exigences de logiciel et de navigateur pour](../../hardware-requirements-for-the-teams-app.md) Teams.
- Version d’électronique de novembre 2018 ou ultérieure

## <a name="set-up-the-teams-ehr-connector"></a>Configurer le connecteur Teams EHR

La configuration du connecteur nécessite que vous :

- [Lancer le portail de configuration du connecteur EHR](#launch-the-ehr-connector-configuration-portal)
- [Entrer les informations de configuration](#enter-configuration-information)
- [Activer les notifications SMS (facultatif)](#enable-sms-notifications-optional)
- [Passer en revue et terminer la configuration](ehr-admin-cerner.md#review-and-finish-the-configuration)

> [!IMPORTANT]
> Ces étapes doivent être effectuées par l’Microsoft 365 administrateur global de votre organisation.  

### <a name="launch-the-ehr-connector-configuration-portal"></a>Lancer le portail de configuration du connecteur EHR

Pour commencer, votre administrateur Microsoft 365 ouvre le portail de configuration du connecteur [EHR](https://ehrconnector.teams.microsoft.com) et se connecte à l’aide de ses informations d’identification Microsoft.

Votre Microsoft 365 administrateur peut configurer un ou plusieurs services pour tester l’intégration. Configurez l’URL de test et de production dans le portail de configuration. Avant de passer à la production, veillez à tester l’intégration à partir de l’environnement de test Cerner.

### <a name="enter-configuration-information"></a>Entrer les informations de configuration

Ensuite, pour configurer l’intégration, votre administrateur Microsoft 365 ajoute une URL de base des ressources Fast Health Interoperability (F URL) à partir d’Cerner et spécifie l’environnement. Configurez autant d’URL de base FEMBA que nécessaire, selon les besoins de votre organisation et les environnements que vous voulez tester.

:::image type="content" source="media/ehr-admin-cerner-configuration.png" alt-text="Capture d’écran de la page Informations sur la configuration du Teams de configuration du connecteur EHR." lightbox="media/ehr-admin-cerner-configuration.png":::

- L’URL de base FEMBA est une adresse statique qui correspond au point de terminaison de l’API FEMBA de votre serveur. Exemple d’URL est `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.

- Vous pouvez configurer l’intégration pour les environnements de test et de production. Pour la configuration initiale, nous vous encourageons à configurer le connecteur à partir d’un environnement de test avant de passer à la production.

Une fois l’URL de base FEMBA validée et l’environnement sélectionné, sélectionnez **Terminé**. Ensuite, ajoutez d’autres URL de base FEMBA pour d’autres environnements, selon les besoins.

**Sélectionnez Suivant** pour passer à l’étape suivante.

### <a name="enable-sms-notifications-optional"></a>Activer les notifications SMS (facultatif)

Terminez cette étape si votre organisation souhaite que Microsoft gère les notifications SMS pour vos patients. Lorsque vous activez les notifications SMS, vos patients reçoivent des messages de confirmation et de rappel pour les visites programmées.

Pour activer les notifications SMS, votre Microsoft 365 de messagerie doit :

1. Sur la page notifications SMS, sélectionnez les deux boîtes à cocher de consentement pour :

    - Autorisez Microsoft à envoyer des notifications PAR SMS à des patients au nom de votre organisation.
    - Reconnaissez que vous devez vous assurer que les participants ont accepté d’envoyer et de recevoir des SMS.

    :::image type="content" source="media/ehr-admin-cerner-sms-notifications.png" alt-text="Capture d’écran de la page des notifications SMS, montrant les cases à cocher de consentement et l’option de générer un numéro de téléphone." lightbox="media/ehr-admin-cerner-sms-notifications.png":::

1. Sous **Vos numéros de téléphone**, **sélectionnez Générer un nouveau numéro de** téléphone pour générer un numéro de téléphone pour votre organisation. Cette opération lance le processus de demande et de génération d’un nouveau numéro de téléphone. Ce processus peut prendre jusqu’à 2 minutes.

    Une fois le numéro de téléphone généré, il s’affiche à l’écran. Ce numéro sera utilisé pour envoyer des confirmations par SMS et des rappels à vos patients. Le numéro a été mis en service, mais n’est pas encore lié à l’URL de base F URL. Vous devez le faire au cours de l’étape suivante.

    :::image type="content" source="media/ehr-admin-cerner-phone-number.png" alt-text="Capture d’écran montrant un exemple du numéro de téléphone généré." lightbox="media/ehr-admin-cerner-phone-number.png":::

    **Sélectionnez Terminé**, puis **Suivant**.

1. Pour lier le numéro de téléphone à une URL de base FEMBA, sous Téléphone **numéro** dans la section **configuration SMS**, sélectionnez le numéro. Faites cette étape pour chaque URL de base FEMBA pour laquelle vous voulez activer les notifications SMS.

    :::image type="content" source="media/ehr-admin-cerner-link-phone-number.png" alt-text="Capture d’écran montrant comment lier un numéro de téléphone à une URL de base F URL." lightbox="media/ehr-admin-cerner-link-phone-number.png":::

    Si c’est la première fois que vous configurez le connecteur, l’URL de base FEMBA qui a été entrée à l’étape précédente s’affichera. Le même numéro de téléphone peut être lié à plusieurs URL de base FEMBA, ce qui signifie que les patients reçoivent des notifications SMS en provenance du même numéro de téléphone pour différentes organisations et/ou services.

     **Sélectionnez Suivant**.

### <a name="review-and-finish-the-configuration"></a>Passer en revue et terminer la configuration

Des enregistrements d’intégration pour le lancement du patient et du fournisseur vous sont présentés. Ces enregistrements sont nécessaires pour effectuer la configuration des visites virtuelles dans Cerner. Pour plus d’informations, voir le guide Cerner-Microsoft Teams’intégration télésantantant.

> [!NOTE]
> À tout moment, votre Microsoft 365 de configuration peut se connecter au portail de configuration pour afficher les enregistrements d’intégration et modifier les paramètres de configuration, si nécessaire.

## <a name="launch-teams-virtual-visits"></a>Lancer Teams visites virtuelles

À l’issue des étapes du connecteur EHR et des étapes de configuration d’cerner, votre organisation est prête à prendre en charge les visites vidéo avec Teams.

### <a name="virtual-visits-prerequisites"></a>Conditions préalables pour les visites virtuelles

- Vos systèmes doivent satisfaire toutes [les exigences logicielles et de navigateur pour](../../hardware-requirements-for-the-teams-app.md) Teams.
- Vous avez effectué la configuration de l’intégration entre l’organisation Cerner et Microsoft 365 organisation.

### <a name="provider-experience"></a>Expérience fournisseur

Les fournisseurs de soins de santé de votre organisation peuvent participer à des visites via Teams depuis le portail PowerChart. Le fournisseur doit accéder au tableau des patients dans lequel l’option Teams patient est disponible.

À partir de là, le fournisseur peut consulter les informations de visite, rejoindre les visites et envoyer le lien de la réunion. Après la première inscription, le fournisseur est directement placé sur le rendez-vous virtuel dans Teams.

Principales fonctionnalités de l’expérience fournisseur :

- Les fournisseurs peuvent rejoindre des visites à l’aide de navigateurs pris en charge ou de l Teams appe.
- Les fournisseurs peuvent utiliser toutes les fonctionnalités de réunion Teams prise en charge, y compris le partage d’écran, l’arrière-plan personnalisé et l’enregistrement.
- Les fournisseurs peuvent voir les mises à jour en temps réel des patients se connectant à une visite pour un rendez-vous donné dans PowerChart.
- Les informations du fournisseur ne sont pas visibles pour les patients pendant la visite.

> [!NOTE]
> Toute information entrée dans la conversation de réunion nécessaire à des fins de continuité ou de rétention des dossiers médicaux doit être téléchargée, copiée et notée par le fournisseur de soins de santé. La conversation ne constitue pas un dossier médical ni un jeu de dossiers désigné. Les messages de la conversation sont stockés en fonction des paramètres créés par l’Microsoft Teams conversation.

### <a name="patient-experience"></a>Expérience patient

Le connecteur prend en charge les patients rejoignant des visites via un lien dans le SMS. Au moment du rendez-vous, les patients peuvent commencer une visite en appuyant sur le lien dans le SMS.

Principales fonctionnalités de l’expérience des patients

- Les patients peuvent rejoindre des visites à partir de navigateurs web modernes sur un ordinateur de bureau ou un appareil mobile sans avoir [à installer Teams’application](../mobile-browser-join.md).
- Les patients peuvent rejoindre les visites d’un simple clic sans qu’aucune autre compte ou aucune autre inscription ne soit nécessaire.
- Les patients n’ont pas besoin de créer un compte Microsoft ou de se connecter pour lancer une visite.
- Les patients sont placés dans une salle d’accueil jusqu’à ce que le fournisseur les rejoigne et les admette.
- Les patients peuvent tester leur vidéo et leur microphone dans la salle d’accueil avant de rejoindre la visite.

## <a name="privacy-and-location-of-data"></a>Confidentialité et emplacement des données

Teams’intégration aux systèmes EHR optimise la quantité de données utilisées et stockées pendant les flux d’intégration et de visites virtuelles. La solution respecte les principes et les directives générales de Teams en matière de confidentialité et de gestion des données, décrits dans Confidentialité Teams.

Le connecteur Teams EHR ne stocke ni ne transfère aucune donnée personnelle identifiable ou les dossiers médicaux des patients ou fournisseurs de soins à partir du système EHR. Les seules données que le connecteur EHR stocke sont l’ID unique de l’utilisateur EHR, qui est utilisé lors Teams configuration de la réunion.

L’ID unique de l’utilisateur DMI est stocké dans l’une des trois zones géographiques décrites dans [Emplacement de stockage des données client Microsoft 365](/microsoft-365/enterprise/o365-data-locations). Toutes les conversations, enregistrements et autres données partagées dans Teams par les participants à la réunion sont stockées conformément aux stratégies de stockage existantes. Pour en savoir plus sur l’emplacement des données dans Teams, voir Emplacement des données [dans Teams](../../location-of-data-in-teams.md).

## <a name="related-articles"></a>Articles connexes

- [Teams rapports d’administrateur du connecteur EHR](ehr-admin-reports.md)
- [Commencer à travailler avec Teams pour les organisations de soins de santé](teams-in-hc.md)
