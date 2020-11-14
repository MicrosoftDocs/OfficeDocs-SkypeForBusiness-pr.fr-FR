---
title: Utiliser le planificateur de réseaux pour Microsoft teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 06/24/2019
ms.topic: article
ms.service: msteams
ms.reviewer: svemu
audience: admin
description: L’administrateur peut en savoir plus sur l’utilisation du planificateur de réseau pour déterminer la configuration requise pour le réseau de Microsoft Teams.
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
ms.openlocfilehash: 14bdc08656cdce18fc25b38ca8d226ac0e70cf27
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030620"
---
# <a name="use-the-network-planner-for-microsoft-teams"></a>Utiliser le planificateur de réseaux pour Microsoft teams

Le planificateur de réseaux est un nouvel outil disponible dans le centre d’administration Teams. Vous pouvez le trouver en accédant **à Planner**  >  **Network Planner**. En quelques étapes seulement, le planificateur de réseaux peut vous aider à déterminer et organiser les exigences réseau pour la connexion des utilisateurs Microsoft teams au sein de votre organisation. Lorsque vous fournissez les informations relatives à votre réseau et à l’utilisation des équipes, le planificateur réseau calcule la configuration requise pour le déploiement d’équipes et de la voix Cloud dans les emplacements physiques de votre organisation.

![Capture d’écran du planificateur de réseaux](media/network-planner.png)

Le planificateur réseau vous permet d’effectuer les opérations suivantes :

- Créer des représentations de votre organisation à l’aide de sites et de personnes recommandées Microsoft (travailleurs Office, travailleurs à distance et systèmes de salle Teams).

    > [!NOTE]
    > Les personnes recommandées ont été développées en fonction des données des scénarios d’utilisation et de modèles d’utilisation les plus courants. Toutefois, vous pouvez créer jusqu’à trois personnages personnalisés en plus des trois personnages recommandés.

- Générez des rapports et calculez les besoins en bande passante pour l’utilisation des équipes.

Pour utiliser le planificateur réseau, vous devez être administrateur général, administrateur de service teams ou administrateur de communications Teams.

## <a name="create-a-custom-persona"></a>Créer un personnage personnalisé

Pour créer un personnage personnalisé, procédez comme suit :

1. Accédez au planificateur de réseau dans le centre d’administration Microsoft Teams.

2. Dans l’onglet **personnages** , cliquez sur **+ personnalisé**. 

3. Dans le **nouveau volet de personnages personnalisé** , ajoutez un nom et une description pour le nouveau personnage.

4. Sélectionnez les autorisations que ce personnage utilisera au sein de l’organisation.

5. Cliquez sur **Enregistrer**.

## <a name="build-your-plan"></a>Créer votre plan

Pour commencer à créer votre plan réseau, procédez comme suit :

1. Accédez au planificateur de réseau dans le centre d’administration Microsoft Teams.

2. Dans l’onglet **plan réseau** , cliquez sur **Ajouter un plan réseau**.

3. Entrez le nom et la description de votre plan réseau. Le plan du réseau doit apparaître dans la liste des offres disponibles.

4. Cliquez sur le nom du plan pour sélectionner le nouveau plan.

5. Ajoutez des sites pour créer une représentation de la configuration réseau de votre organisation.

    En fonction du réseau de votre organisation, vous souhaiterez peut-être utiliser des sites pour représenter un bâtiment, un emplacement de bureau ou un autre emplacement. Les sites peuvent être connectés par un réseau étendu pour autoriser le partage de connexions Internet et/ou PSTN. Pour obtenir de meilleurs résultats, créez des sites avec des connexions locales avant de créer des sites qui se connectent à distance à Internet ou PSTN.

    Pour créer un site :

    1. Ajoutez un nom et une description pour votre site.

    2. Sous **paramètres réseau** , ajoutez le nombre d’utilisateurs du réseau sur ce site (obligatoire).

    3. Ajoutez des informations sur le réseau : accès WAN, capacités WAN, sortie Internet ( **locale** ou **distante** ), sortie PSTN (aucun, local ou distant).

      > [!NOTE]
      > Vous devez ajouter des numéros de capacités WAN et Internet pour afficher des recommandations en matière de bande passante spécifiques lors de la génération d’un rapport.

    4. Cliquez sur **Enregistrer**.

## <a name="create-a-report"></a>Créer un rapport

Après avoir ajouté tous les sites, vous pouvez créer un rapport, comme suit.

1. Dans l’onglet **rapports** , cliquez sur **Démarrer un rapport**.

2. Pour chaque site que vous créez, distribuez le nombre d’utilisateurs au sein des personnages disponibles. Si vous utilisez les personnages recommandés par Microsoft, le numéro sera distribué automatiquement (80% du travailleur et 20% du travailleur distant).

3. Lorsque vous avez terminé la distribution, cliquez sur **générer le rapport**.

    Le rapport généré affiche les exigences de bande passante dans plusieurs affichages de sorte que vous puissiez clairement comprendre la sortie :
    - Une table avec des calculs individuels affichera les exigences de bande passante pour chaque activité autorisée.
    - Un affichage supplémentaire affiche les recommandations globales en matière de bande passante.

4. Cliquez sur **Enregistrer**. Votre rapport sera disponible dans la liste des rapports pour un affichage ultérieur.

## <a name="example-scenario"></a>Exemple de scénario

Pour obtenir un exemple de l’utilisation du planificateur de réseaux pour configurer un plan réseau et générer un rapport à l’aide de ces étapes, téléchargez le [Planificateur de réseaux How-To présentation PowerPoint](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/network-planner-how-to.pptx?raw=true) (en anglais uniquement).
