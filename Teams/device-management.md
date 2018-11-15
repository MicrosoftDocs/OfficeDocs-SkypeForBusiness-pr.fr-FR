---
title: Gérer vos périphériques dans Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 11/12/2018
ms.topic: article
ms.service: msteams
ms.reviewer: kelsawi
f1keywords: ms.teamsadmincenter.devicemanagement.overview
description: Découvrez comment gérer les périphériques utilisés dans les équipes de votre organisation.
localization_priority: Normal
appliesto:
- Microsoft Teams
ms.openlocfilehash: 97fd4b8d7f613c6d3f435f2d505bbd2cf99d4b10
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/15/2018
ms.locfileid: "26531775"
---
# <a name="manage-your-devices-in-microsoft-teams"></a>Gérer vos périphériques dans Microsoft Teams

 En tant qu’administrateur, vous gérez tous les périphériques utilisés dans les équipes de votre organisation depuis le centre Microsoft Teams & Skype pour entreprise centre d’administration. Vous pouvez afficher et gérer l’inventaire des appareils pour votre organisation et effectuer des tâches telles que la mise à jour, de redémarrage et surveiller les diagnostics pour les appareils. Vous pouvez également créer et affecter des profils de configuration pour un périphérique ou des groupes de périphériques. 

## <a name="what-devices-can-you-manage"></a>Quels appareils pouvez-vous gérer ?
Appareils doivent être certifiées pour les équipes et inscrit dans les équipes. Un périphérique est inscrit automatiquement la première fois qu’un utilisateur se connecte aux équipes sur l’appareil. 

> [!NOTE]
> Si vous avez Microsoft Intune, périphériques sont automatiquement inscrits dans Intune. Une fois un périphérique est inscrit, conformité périphérique est confirmée et stratégies d’accès conditionnel sont appliquées à l’appareil. 

## <a name="manage-devices-in-teams"></a>Gérer les périphériques dans les équipes

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) Avec le modèle Microsoft Teams & Skype entreprise centre d’administration

1. Dans la navigation de gauche, accédez à des **périphériques** > **Gestion de périphériques**.
2. Sélectionnez **tous les périphériques**.  

 À partir de là, vous pouvez afficher et gérer tous les périphériques inscrits dans les équipes de votre organisation. Les informations qui s’affichent pour chaque périphérique incluent l’historique, fabricant, modèle, utilisateur, état, action, dernière apparaît et nom du périphérique. Vous pouvez personnaliser l’affichage pour afficher les informations qui correspond le mieux à vos besoins.

 Voici quelques exemples de la façon de gérer les périphériques équipes au sein de votre organisation.  
    
|Pour ce faire...  |Cela |
|---------|---------|
|Modifier les informations de périphérique   | Sélectionnez un périphérique > **Modifier**. Vous pouvez modifier les détails tels que le nom du périphérique, les informations utilisateur, numéro d’identification et ajouter des notes.     |
|Gérer les mises à jour logicielles   |Sélectionnez un périphérique > **mise à jour**. Vous pouvez afficher la liste des mises à jour de logiciels et de microprogrammes, disponibles pour le périphérique et cliquez sur Installer les mises à jour.    |
|Redémarrer un appareil   |Sélectionnez un périphérique > **redémarrer**.          |
|Afficher l’historique du périphérique  | Sélectionnez un périphérique > **historique**. Vous pouvez afficher l’historique de mise à jour du périphérique.     |
|Afficher des diagnostics  | Sélectionnez un périphérique > **Diagnostics**.        |

## <a name="use-configuration-profiles-in-teams"></a>Utilisation des profils de configuration dans les équipes

Utilisez les profils de configuration pour gérer les paramètres et les fonctionnalités pour les périphériques des équipes au sein de votre organisation. Vous pouvez créer ou télécharger des profils de configuration pour inclure les paramètres et les fonctionnalités que vous souhaitez activer ou désactiver et affecter un profil à un appareil ou des groupes de périphériques. 

### <a name="create-a-configuration-profile"></a>Créer un profil de configuration

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) Avec le modèle Microsoft Teams & Skype entreprise centre d’administration

1. Dans la navigation de gauche, accédez à des **périphériques** > **Gestion de périphériques**.
2. Sélectionnez **les profils de Configuration**, puis sélectionnez le **profil de configuration**.
3. Entrez un nom pour le profil et si vous le souhaitez, ajoutez une description conviviale.
4. Spécifier les paramètres souhaités pour le profil, puis cliquez sur **Enregistrer**.

### <a name="assign-a-configuration-profile"></a>Affecter un profil de configuration

![les équipes-logo-30x30.png](media/teams-logo-30x30.png) Avec le modèle Microsoft Teams & Skype entreprise centre d’administration

1. Dans la navigation de gauche, accédez à des **périphériques** > **Gestion de périphériques**.
2. Sélectionnez le **profil de Configuration**, puis cliquez sur le lien sous **affecté à** dans le profil que vous voulez affecter.  
3. Dans le volet **affecter des périphériques à un profil de configuration** , recherchez et sélectionnez les périphériques que vous voulez attribuer.
4. Cliquez sur **Enregistrer**.
