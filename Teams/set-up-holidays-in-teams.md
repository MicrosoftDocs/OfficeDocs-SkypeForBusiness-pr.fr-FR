---
title: Configurer des jours fériés dans Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
description: Découvrez comment configurer les jours fériés dans Microsoft Teams et les connecter à votre standard automatique.
ms.openlocfilehash: afec7fc3f1bbe47c907b823711db3b8b8ef3aded
ms.sourcegitcommit: 6949c957224949ccc6f5958d3c84294d382ee405
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/18/2019
ms.locfileid: "31914577"
---
# <a name="set-up-holidays-in-microsoft-teams"></a>Configurer des jours fériés dans Microsoft Teams

Vous pouvez utiliser la fonctionnalité de congés des équipes Microsoft pour planifier les dates spécifiques et de lorsque les personnes de votre organisation seront être prenez des congés à partir de travail n’est pas disponible pendant les heures ouvrables. 

Vous pouvez lier les congés à standards automatiques que vous créez au sein de votre organisation. Standards automatiques de permettent aux appelants de naviguer d’un système de menus pour atteindre le bon service ou d’obtenir les informations dont ils ont besoin. Lorsque vous configurez les paramètres d’appel congé pour un standard automatique, vous pouvez sélectionnez le jour férié à partir d’une liste, ajouter un message d’accueil et spécifier que faire avec l’appel lorsque celui-ci est reçu par le standard automatique au cours de la période de congé.

Un bon exemple consiste à créer un congé pour Noël pour lorsque beaucoup de vos employés ne sont pas au bureau. Après avoir créer la période de congé et définir les heures, puis vous devez ajouter le congé à votre principale standard automatique afin que lors de l’appellent de personnes, elles seront entendre un message audio que vous avez créé. Quelque chose comme, « nous effectuons fermés de Noël de 22 décembre via 27 décembre. Laissez nous un message vocal afin que nous pouvons renvoyer votre appel lorsque nous sommes du bureau. »

Pour plus d’informations sur les standards automatiques, voir [Quelles sont les standards automatiques de nuage](what-are-phone-system-auto-attendants.md)?  

## <a name="create-a-holiday"></a>Créer une période de congé

1. Dans le centre d’administration Microsoft Teams, accédez à **paramètres à l’échelle de l’organisation** > **jours fériés**.

2. Sélectionnez **Nouveau congé**.

3. Entrez un nom pour la période de congé.

4. Sélectionnez **Ajouter nouvelle date**.

5. Sous **heure de début**, sélectionnez l’icône du calendrier, sélectionnez la date lorsque vous souhaitez que le congé pour commencer.

6. Utilisez la liste déroulante pour sélectionner une heure de début pour la période de congé.

7. Sous **heure de fin**, sélectionnez l’icône du calendrier, sélectionnez la date lorsque vous souhaitez que le congé à la fin. Si le congé n’est qu’un jour, il doit s’agir de la même date que celui que vous avez choisi sous **heure de début**.

8. Utilisez la liste déroulante pour sélectionner une heure de fin pour la période de congé.

9. Cliquez sur **Enregistrer**.

## <a name="change-a-holiday"></a>Modifier une période de congé

1. Dans le centre d’administration Microsoft Teams, accédez à **paramètres à l’échelle de l’organisation** > **jours fériés**.

2. Dans la liste, sélectionnez la période de congé.

3. Sous **heure de début**, sélectionnez l’icône du calendrier, sélectionnez la date lorsque vous souhaitez que le congé pour commencer.

4. Utilisez la liste déroulante pour sélectionner une heure de début pour la période de congé.

5. Sous **heure de fin**, sélectionnez l’icône du calendrier, sélectionnez la date lorsque vous souhaitez que le congé à la fin. 

6. Utilisez la liste déroulante pour sélectionner une heure de fin pour la période de congé.

7. Cliquez sur **Enregistrer**.

## <a name="connect-a-holiday-to-an-auto-attendant"></a>Connecter un congé à un standard automatique

1. Dans le centre d’administration Microsoft Teams, accédez à la **voix** > **standards automatiques**.
2. Sélectionnez un compte de ressource dans la liste.
3. Dans le volet gauche, sélectionnez **Paramètres des appels de congé**.
4. Sélectionnez **Nouveau congé**.
5. Dans la liste déroulante, sélectionnez la période de congé.
6. Vous pouvez ajouter un message d’accueil facultatif :
    - Pour lire un message d’accueil enregistré, sélectionnez **lire un fichier audio**, puis sélectionnez **Télécharger le fichier**. Accédez à l’emplacement du fichier audio, sélectionnez le fichier, puis sélectionnez **Ouvrir**.
    - Pour créer un message d’accueil, sélectionnez le **Type d’un message de bienvenue**, puis tapez votre message. Les appelants entendent ce message si vous n’avez pas fourni d’un fichier audio.
7. Pour mettre fin à l’appel après le message d’accueil, sous **Actions**, sélectionnez **se déconnecter**. 

    Pour rediriger l’appel, sélectionnez **rediriger l’appel**, puis sélectionnez la personne qui recevra l’appel redirigé à partir de la liste déroulante ou de la recherche pour la personne par nom complet.
8. Cliquez sur **Enregistrer**.

## <a name="related-topics"></a>Rubriques connexes

[Quelles sont les standards automatiques de nuage](what-are-phone-system-auto-attendants.md)?