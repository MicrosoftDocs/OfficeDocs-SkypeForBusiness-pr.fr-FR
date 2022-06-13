---
title: Utiliser le Planificateur de réseau pour Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: L’administrateur peut apprendre à utiliser le Planificateur de réseau pour déterminer la configuration réseau requise pour Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- m365initiative-deployteams
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.networkplanner.overview
- ms.teamsadmincenter.networkplanner.personas
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: fba570bdd7a83c26d68d10e65f631a0d028d7408
ms.sourcegitcommit: 91cfb1a9c527d605300580c3acad63834ee54682
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/13/2022
ms.locfileid: "66045553"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Utiliser le Planificateur de réseau pour Microsoft Teams

Network Planner est un nouvel outil disponible dans le centre d’administration Teams. Vous pouvez le trouver en vous rendant dans le **Planificateur de réseau** **de planification** > . En quelques étapes, le Planificateur de réseau peut vous aider à déterminer et à organiser les exigences réseau pour connecter Microsoft Teams utilisateurs au sein de votre organisation. Lorsque vous indiquez les détails de votre réseau et de votre utilisation de Teams, le planificateur de réseau calcule les exigences réseau requises pour le déploiement de Teams et de Voix Cloud dans les emplacements physiques de votre organisation.

![Capture d’écran du Planificateur de réseaux.](media/network-planner.png)

Le planificateur de réseau vous permet d’effectuer les opérations suivantes :

- Créez des représentations de votre organisation à l’aide de sites et de personnages recommandés par Microsoft (employés de bureau, travailleurs à distance et système de salle Teams).

    > [!NOTE]
    > Les personnages recommandés ont été développés en fonction des données de Teams scénarios d’utilisation optimale et des modèles d’utilisation classiques. Toutefois, vous pouvez créer jusqu’à trois personnages personnalisés en plus des trois personnages recommandés.

- Générez des rapports et calculez les besoins en bande passante pour Teams utilisation.

Pour utiliser le Planificateur de réseau, vous devez être administrateur général, administrateur Teams ou administrateur de communications Teams.

## <a name="create-a-custom-persona"></a>Créer un personnage personnalisé

Procédez comme suit pour créer un personnage personnalisé :

1. Accédez au Planificateur de réseau dans le centre d’administration Microsoft Teams.

2. Sous l’onglet **Personas** , cliquez sur **+ Persona personnalisé**. 

3. Dans le volet **Nouveau personnage personnalisé** , ajoutez un nom et une description pour le nouveau personnage.

4. Sélectionnez les autorisations que ce personnage utilisera au sein de l’organisation.

5. Cliquez sur **Enregistrer**.

## <a name="build-your-plan"></a>Créer votre plan

Procédez comme suit pour commencer à créer votre plan réseau :

1. Accédez au Planificateur de réseau dans le centre d’administration Microsoft Teams.

2. Sous l’onglet **Plan réseau** , cliquez sur **Ajouter un plan réseau**.

3. Entrez un nom et une description pour votre plan réseau. Le plan réseau s’affiche dans la liste des plans disponibles.

4. Cliquez sur le nom du plan pour sélectionner le nouveau plan.

5. Ajoutez des sites pour créer une représentation de la configuration réseau de votre organisation.

    Selon le réseau de votre organisation, vous pouvez utiliser des sites pour représenter un bâtiment, un emplacement de bureau ou autre chose. Les sites peuvent être connectés par un wan pour permettre le partage de connexions Internet et/ou RTC. Pour de meilleurs résultats, créez des sites avec des connexions locales avant de créer des sites qui se connectent à distance à Internet ou à PSTN.

    Pour créer un site :

    1. Ajoutez un nom et une description pour votre site.

    2. Sous **Paramètres réseau**, ajoutez le nombre d’utilisateurs réseau sur ce site (obligatoire).

    3. Ajoutez les détails du réseau : wan activé, capacité WAN, sortie Internet (**local** ou **distant**) et sortie RTC (aucun, local ou distant).

      > [!NOTE]
      > Vous devez ajouter des numéros de capacité WAN et Internet pour afficher des recommandations de bande passante spécifiques lorsque vous générez un rapport.

    4. Cliquez sur **Enregistrer**.

## <a name="create-a-report"></a>Créer un rapport

Après avoir ajouté tous les sites, vous pouvez créer un rapport, comme suit.

1. Sous l’onglet **Rapports** , cliquez sur **Démarrer un rapport**.

2. Pour chaque site que vous créez, distribuez le nombre d’utilisateurs sur les personnages disponibles. Si vous utilisez les personas recommandées par Microsoft, le numéro sera distribué automatiquement (80 % de travailleurs du bureau et 20 % de travailleurs distants).

3. Une fois la distribution terminée, cliquez sur **Générer le rapport**.

    Le rapport généré affiche les exigences de bande passante dans plusieurs affichages différents afin que vous puissiez comprendre clairement la sortie :
    - Une table avec des calculs individuels affiche les exigences de bande passante pour chaque activité autorisée.
    - Une vue supplémentaire affiche les besoins globaux en bande passante avec des recommandations.

4. Cliquez sur **Enregistrer**. Votre rapport sera disponible dans la liste des rapports pour une consultation ultérieure.

## <a name="example-scenario"></a>Exemple de scénario

Pour obtenir un exemple d’utilisation du planificateur de réseaux pour configurer un plan réseau et générer un rapport à l’aide de ces étapes, téléchargez le planificateur [de réseau How-To PowerPoint jeu](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (en anglais uniquement).
