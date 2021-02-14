---
title: Utiliser le Planificateur réseau pour Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: Les administrateurs peuvent découvrir comment utiliser le Planificateur réseau pour déterminer la exigences réseau pour Microsoft Teams.
localization_priority: Normal
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
ms.openlocfilehash: 9351c37c96e4bc11f0e5f93041f7e024158d7564
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611798"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Utiliser le Planificateur réseau pour Microsoft Teams

Network Planner est un nouvel outil disponible dans le Centre d’administration Teams. Il est possible de le trouver en vous rendre dans **Planificateur**  >  **Réseau de planification.** En quelques étapes, le Planificateur réseau peut vous aider à déterminer et à organiser la exigences réseau pour connecter les utilisateurs de Microsoft Teams au sein de votre organisation. Lorsque vous fournissez les détails de votre réseau et que vous fournissez l’utilisation de Teams, le Planificateur réseau calcule votre exigences réseau pour déployer Teams et voix cloud sur les emplacements physiques de votre organisation.

![Capture d’écran du Planificateur réseau](media/network-planner.png)

Le Planificateur réseau vous permet d':

- Créez des représentations de votre organisation à l’aide de sites et de personnage recommandés par Microsoft (employés de bureau, employés à distance et système de salle Teams).

    > [!NOTE]
    > Les personnage recommandés ont été développés sur la base de données de scénarios d’utilisation les plus pratiques dans Teams et de modèles d’utilisation classiques. Toutefois, vous pouvez créer jusqu’à trois personnage personnalisés en plus des trois personnage recommandés.

- Générez des rapports et calculez les besoins en bande passante pour l’utilisation de Teams.

Pour utiliser le Planificateur réseau, vous devez être administrateur général, administrateur de services Teams ou administrateur de communications Teams.

## <a name="create-a-custom-persona"></a>Créer un personnage personnalisé

Pour créer un personnage personnalisé, suivez ces étapes :

1. Dans le Centre d’administration Microsoft Teams, allez au Planificateur réseau.

2. Sous **l’onglet Personnage,** cliquez **sur + Personnage personnalisé.** 

3. Dans le **volet Nouveau personnage personnalisé,** ajoutez un nom et une description pour le nouveau personnage.

4. Sélectionnez les autorisations que ce personnage utilisera au sein de l’organisation.

5. Cliquez sur **Enregistrer**.

## <a name="build-your-plan"></a>Créez votre plan

Pour commencer à créer votre plan réseau, suivez les étapes suivantes :

1. Dans le Centre d’administration Microsoft Teams, allez au Planificateur réseau.

2. Sous **l’onglet Plan réseau,** cliquez **sur Ajouter un plan réseau.**

3. Entrez un nom et une description pour votre plan réseau. Le plan réseau s’affiche dans la liste des plans disponibles.

4. Cliquez sur le nom du plan pour sélectionner le nouveau plan.

5. Ajoutez des sites pour créer une représentation de la configuration réseau de votre organisation.

    En fonction du réseau de votre organisation, vous pouvez utiliser des sites pour représenter un bâtiment, un emplacement de bureau ou autre chose. Les sites peuvent être connectés par un réseau WAN pour autoriser le partage des connexions Internet et/ou PSTN. Pour de meilleurs résultats, créez des sites avec des connexions locales avant de créer des sites qui se connectent à distance à Internet ou au réseau PSTN.

    Pour créer un site :

    1. Ajoutez un nom et une description pour votre site.

    2. Sous **Paramètres réseau,** ajoutez le nombre d’utilisateurs réseau sur ce site (obligatoire).

    3. Ajoutez les détails du réseau : activé pour le réseau WAN, la capacité WAN, la sortie Internet **(locale** ou distante) et la sortie PSTN (aucune, locale ou distante).

      > [!NOTE]
      > Vous devez ajouter des numéros de réseau WAN et de capacité Internet pour consulter des recommandations spécifiques en matière de bande passante lorsque vous générez un rapport.

    4. Cliquez sur **Enregistrer**.

## <a name="create-a-report"></a>Créer un état

Après avoir ajouté tous les sites, vous pouvez créer un état comme suit.

1. Sous **l’onglet** Rapports, cliquez **sur Démarrer un rapport.**

2. Pour chaque site que vous créez, distribuez le nombre d’utilisateurs aux différents personnage disponibles. Si vous utilisez les personnage recommandés par Microsoft, le numéro est distribué automatiquement (80 % pour les travailleurs du bureau et 20 % pour les employés à distance).

3. Une fois la distribution terminée, cliquez sur **Générer un rapport.**

    Le rapport généré affiche les besoins en bande passante dans plusieurs affichages différents, de sorte que vous pouvez clairement comprendre le résultat :
    - Une table avec des calculs individuels affiche les besoins en bande passante pour chaque activité autorisée.
    - Un affichage supplémentaire présente les besoins globaux en bande passante avec des recommandations.

4. Cliquez sur **Enregistrer**. Votre rapport sera disponible dans la liste des rapports pour un affichage ultérieur.

## <a name="example-scenario"></a>Exemple de scénario

Pour obtenir un exemple d’utilisation du Planificateur réseau pour configurer un plan réseau et générer un rapport à l’aide de ces étapes, téléchargez le planificateur réseau How-To [présentation PowerPoint](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (en anglais uniquement).
