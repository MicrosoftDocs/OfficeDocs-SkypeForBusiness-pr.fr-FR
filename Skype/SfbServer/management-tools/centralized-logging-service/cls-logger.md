---
title: CLS Logger pour Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/25/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 1eaf8cdf-3dcd-4d6e-ae68-b6f6f9431ad8
description: 'Résumé : Découvrez comment utiliser le journal du Service de journalisation centralisée (CLS) Skype pour Business Server 2015.'
ms.openlocfilehash: 9edaf9d8528e03577fa54bb02f876aac017a4146
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33915002"
---
# <a name="cls-logger-for-skype-for-business-server-2015"></a>CLS Logger pour Skype Entreprise Server 2015
 
**Résumé :** Découvrez comment utiliser le journal du Service de journalisation centralisée (CLS) Skype pour Business Server 2015.
  
CLS Logger est un outil qui vous permet de gérer les journauxdu Service de journalisation centralisée (CLS).
  
## <a name="prerequisites"></a>Conditions requises

Afin de pouvoir utiliser CLS Logger, veillez à ce que les conditions suivantes soient remplies :
  
- Vous utilisez l’outil sur un ordinateur qui est membre du domaine dans lequel le Service de journalisation centralisée (CLS) s’exécute. Pour le moment, l’outil n’est pas compatible avec les sessions PowerShell à distance.
    
- Le fichier Default.tmx issu du dossier de suivi (où résident les données de suivi capturées pour le CLS) et de Snooper doit être copié dans le dossier de l’outil CLS Logger.
    
## <a name="check-the-logging-status-of-a-set-of-poolscomputers"></a>Vérification du statut de journalisation d’un ensemble de pools/ordinateurs

Utiliser les commandes suivantes pour vérifier le statut de journalisation :
  
1. Dans l’onglet « Scénarios Start/Stop », sélectionnez un regroupement de Pools ou d’ordinateurs dans l’arborescence de la topologie.
    
2. Cliquez sur le bouton Statut de journalisation.
    
3. Consultez la sortie de la commande dans la zone de sortie de commande PowerShell contenant les informations spécifiques relatives au statut de journalisation des pools et/ou ordinateurs sélectionnés.
    
## <a name="start-an-existing-scenario"></a>Début d’un scénario existant

Pour lancer un scénario existant :
  
1. Dans l’onglet « Scénarios Start/Stop », sélectionnez un scénario existant dans le menu déroulant de scénarios.
    
2. Sélectionnez un groupe de pools et/ou d’ordinateurs dans l’arborescence Topologie.
    
3. Cliquez sur le bouton Lancer le scénario. L’interface utilisateur est alors désactivée jusqu’à la fin de l’opération. Celle-ci peut durer un certain temps pour les déploiements de grande envergure.
    
4. L’interface utilisateur est réactivée à l’issue du lancement réussi du scénario ; de plus, la zone de sortie de commande PowerShell comporte les informations détaillées relatives à l’action.
    
5. Il peut s’écouler un certain temps avant que le CLS se connecte à la journalisation et que de nouvelles données issues de ce scénario soient collectées.
    
## <a name="stop-an-existing-scenario"></a>Arrêt d’un scénario existant

Pour arrêter un scénario existant :
  
1. Dans l’onglet « Scénarios Start/Stop », sélectionnez un scénario existant dans le menu déroulant de scénarios.
    
2. Sélectionnez un groupe de pools et/ou d’ordinateurs dans l’arborescence Topologie.
    
3. Cliquez sur le bouton Arrêter le scénario. L’interface utilisateur est alors désactivée jusqu’à la fin de l’opération. Celle-ci peut durer un certain temps pour les déploiements de grande envergure.
    
4. L’interface utilisateur est réactivée à l’issue de l’arrêt du scénario ; de plus, la zone de sortie de commande PowerShell comporte les informations détaillées relatives à l’action.
    
![Arrêt et démarrage du journal CLS](../../media/2c4a36c2-b5db-4550-a3b3-41f18e0e2f0c.png)
  
## <a name="search-for-logs"></a>Recherche dans les journaux

Afin de rechercher des journaux, sélectionnez l’onglet « Recherche CLS journaux », cliquez sur le bouton « Recherche journaux » après avoir sélectionné les champs affichés comme indiqué ci-dessous :
  
> **Dossier des fichiers journaux** Dossier d’enregistrement des résultats de la recherche de journaux (obligatoire).
> 
> **Niveau des journaux** Détermine le niveau le plus bas qui sera représenté dans les résultats. Par exemple, si vous sélectionnez Warning, seuls Warning, Error et Fatal seront affichés. Par défaut sur Débogage.
> 
> **Pools** Pools d’ordinateurs sur lesquels effectuer la recherche. Il s’agit des nœuds parents dans l’arborescence (obligatoire).
> 
> **Ordinateurs** Ordinateurs individuels sur lesquels effectuer la recherche. Il s’agit des nœuds enfants dans l’arborescence (obligatoire).
> 
> **Heure de départ** Heure à partir de laquelle le CLS interrogera les journaux (obligatoire).
> 
> **Heure de fin** Heure à partir de laquelle le CLS cessera d’interroger les journaux (obligatoire).
> 
> **Composants** Permet de sélectionner les composants à ajouter à la requête (facultatif).
> 
> **Identifiant de l’appel** Identifiant de l’appel de n’importe quel dialogue SIP sur lequel effectuer le filtrage des informations. Attention, ce champ utilise uniquement des correspondances exactes (facultatif).
> 
> **de la conférence** Identifiant de n’importe quelle conférence sur lequel effectuer le filtrage des informations. Attention, ce champ utilise uniquement des correspondances exactes (facultatif).
> 
> **Adresse IP** Adresse IP sur laquelle effectuer le filtrage des informations. Attention, ce champ utilise uniquement des correspondances exactes (facultatif).
> 
> **Identifiants de corrélation** Instructions de suivi qui sont associées les unes aux autres de manière logique par cet identifiant (facultatif).
> 
> **Numéro de téléphone** Filtrage par numéro de téléphone (facultatif).
> 
> **URI SIP** Filtrage par URI SIP (facultatif).
> 
> **Contenu de message SIP** Filtrage par contenu de message SIP, ce qui implique la recherche de chaîne partielle dans ce champ (facultatif).
> 
> **Correspondre à tous** La recherche utilise l’opérateur logique lorsque cette option est sélectionnée. Définie sur Correspondance exacte pour tous les paramètres.
> 
> **Sauter les journaux réseau** La recherche ignore les journaux réseau lorsque cette option est sélectionnée.
    
![Journaux de recherche CLS](../../media/5793ea3c-6f5f-40ef-8b53-100da831eedf.png)
  
## <a name="create-a-scenario"></a>Création d’un scénario

1. Dans l’onglet **Modifier de scénarios** , cliquez sur le bouton **Créer un scénario** .
    
    > [!NOTE]
    > La création d’un scénario duplique la configuration du scénario actuellement sélectionné. Si vous cliquez sur **Effacer les paramètres** avant de créer un scénario, l’opération est effectuée sans que des composants et des indicateurs soient sélectionnés.
  
2. Entrez le nom du scénario à créer et appuyez sur Entrée ou cliquez sur le bouton OK.
    
3. Le nouveau scénario doit à présent être créé. Lorsque la création réussit, la liste déroulante Scénarios est sélectionnée avec le nouveau scénario.
    
## <a name="modify-a-scenario"></a>Modification d’un scénario

![Capture d’écran représentant un journal CLS pour la modification de scénarios](../../media/abbbcac0-8a2e-48af-a22f-4fee0283a29f.png)
  
1. Sous l’onglet **Modifier les scénarios**, recherchez le scénario à modifier.
    
2. Apportez les modifications souhaitées aux composants, niveaux et indicateurs.
    
3. Cliquez sur **Enregistrer le scénario**.
    
4. Lorsque le scénario est enregistré, il actualise le volet d’informations du scénario avec la configuration mise à jour.
    
## <a name="delete-a-scenario"></a>Suppression d’un scénario

1. Sous l’onglet **Modifier des scénarios**, sélectionnez un scénario existant dans le menu déroulant Scénarios.
    
2. Cliquez sur **Supprimer scénario** pour supprimer le scénario.
    
3. Une fois que vous avez confirmé l’action, le scénario est supprimé.
    

