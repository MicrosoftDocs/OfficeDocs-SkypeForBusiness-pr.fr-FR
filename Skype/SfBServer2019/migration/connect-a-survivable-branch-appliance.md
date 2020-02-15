---
title: Connexion d’un Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Chaque Survivable Branch Appliance (SBA) est associé à un pool frontal qui sert de serveur d’inscriptions de sauvegarde pour le SBA. Lorsque le pool frontal est migré vers Skype entreprise Server 2019, le SBA doit être désactivée du pool frontal pendant la mise à niveau du pool, une fois que le pool a été migré vers Skype entreprise Server 2019, le SBA peut être réassocié à l’avant-dernier. ND du pool. Cela implique de supprimer le SBA de la topologie héritée dans le générateur de topologie, puis d’ajouter le SBA à la topologie Skype entreprise Server 2019. Les utilisateurs hébergés sur le SBA hérité doivent d’abord être déplacés vers un autre pool frontal avant de supprimer le SBA de la topologie. Une fois que le SBA est ajouté à la topologie Skype entreprise Server 2019, ces utilisateurs peuvent ensuite être déplacés vers le SBA. Voici un récapitulatif de ces étapes :'
ms.openlocfilehash: 7f51b9c29d6008ea3606184eb22741a489d056df
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027785"
---
# <a name="connect-a-survivable-branch-appliance"></a>Connexion d’un Survivable Branch Appliance

Chaque Survivable Branch Appliance (SBA) est associé à un pool de serveurs frontaux qui sert de serveur d’inscriptions de sauvegarde pour le SBA. Lorsque le pool frontal est migré vers Skype entreprise Server 2019, le SBA doit être désassocié du pool frontal pendant la mise à niveau du pool. Une fois le pool migré vers Skype entreprise Server 2019, le SBA peut être réassocié au pool frontal mis à niveau. Cela implique de supprimer le SBA de la topologie héritée dans le générateur de topologie, puis d’ajouter le SBA à la topologie Skype entreprise Server 2019. Les utilisateurs hébergés sur le SBA hérité doivent d’abord être déplacés vers un autre pool frontal avant de supprimer le SBA de la topologie. Une fois que le SBA est ajouté à la topologie Skype entreprise Server 2019, ces utilisateurs peuvent être déplacés vers le SBA. Voici un récapitulatif de ces étapes :
  
1. Déplacez les utilisateurs de succursale hébergés sur l’SBA hérité dans un autre pool frontal.
    
2. Supprimez SBA de la topologie héritée pour déconnecter le pool frontal existant en tant que serveur d’inscriptions de sauvegarde.
    
3. Ajoutez SBA à la topologie Skype entreprise Server 2019 et configurez ce nouveau pool frontal comme serveur d’inscriptions de sauvegarde. 
    
4. Déplacez les utilisateurs de succursale vers le nouveau Skype entreprise Server 2019 SBA.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Ajouter un site de succursale hérité SBA à votre topologie

1. Ouvrez le **Générateur de topologie**.
    
2. Dans le volet de gauche, cliquez avec le bouton droit sur **sites de succursale**, puis cliquez sur **nouveau site de succursale**.
    
3. Dans la boîte de dialogue **Définir un nouveau site de succursale**, cliquez sur **Nom**, puis tapez le nom du site de succursale.
    
4. (Facultatif) Cliquez sur **Description**, puis tapez une description explicite pour le site de succursale.
    
5. Cliquez sur **Suivant**.
    
6. (Facultatif) Dans la boîte de dialogue **Définir un nouveau site de succursale** qui suit, effectuez l’une des opérations suivantes : 
    
    1. Cliquez sur **Ville**, puis tapez le nom de la ville dans laquelle se trouve le site de succursale.
    
    2. Cliquez sur **Dép./Région**, puis tapez le nom du département ou de la région où se trouve le site de succursale.
    
    3. Cliquez sur **Code du pays**, puis tapez le code d’appel à deux chiffres du pays ou de la région du site de succursale.
    
7. Cliquez sur **suivant**, puis, si vous utilisez un Survivable Branch Appliance ou serveur sur ce site, veillez à désactiver la case à cocher **ouvrir l’Assistant Nouveau Survivable** Branch Server à la fermeture de cet Assistant. Cliquez sur**Terminer**.
    
8. Pour associer le SBA hérité au pool frontal Skype entreprise Server 2019, procédez comme suit :
    
    1. Développez le site de succursale créé. 
    
    2. Cliquez avec le bouton droit sur version héritée, puis cliquez sur **nouveau**.
    
    3. Cliquez sur **Survivable Branch Appliance**.
    
9. Suivez les instructions de l’Assistant qui s’ouvre. Pour plus d’informations sur les éléments de l’Assistant, voir    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Un Survivable Branch Appliance ne peut être associé qu’à un magasin de surveillance. 
  
10. Si vous n’utilisez pas de SBA ou de serveur sur ce site, désactivez la case à cocher **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant**, puis cliquez sur **Terminer**.
    
11. Répétez les étapes précédentes pour chaque site de succursale que vous voulez ajouter à la topologie.
    

