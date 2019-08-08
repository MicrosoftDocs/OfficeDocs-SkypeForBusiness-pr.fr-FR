---
title: Connexion d’une Survivable Branch Appliance
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Chaque appareil de branchement survivant (SBA) est associé à une réserve frontale qui sert de bureau d’enregistrement de sauvegarde pour le SBA. Lorsque le pool frontal est migré vers Skype entreprise Server 2019, l’SBA doit être désassocié du pool frontal lors de la mise à niveau du pool, une fois que le regroupement a été déplacé vers Skype entreprise Server 2019, l’adresse SBA peut être réassociée au premier plan. Pool ND. Cela implique la suppression de l’SBA de la topologie héritée dans le générateur de topologie, puis l’ajout de l’SBA à la topologie 2019 de Skype entreprise Server. Les utilisateurs hébergés sur l’ancien SBA doivent d’abord être déplacés vers un autre pool frontal avant de supprimer l’SBA de la topologie. Une fois que le SBA a été ajouté à la topologie 2019 de Skype entreprise Server, il peut ensuite être ramené à l’adresse SBA. Ces étapes sont décrites ci-dessous:'
ms.openlocfilehash: e5545a2de4eddd65790f425ab888b8fd07faf970
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239283"
---
# <a name="connect-a-survivable-branch-appliance"></a>Connexion d’une Survivable Branch Appliance

Chaque appareil branche survivant (SBA) est associé à un pool frontal qui sert de bureau d’enregistrement de sauvegarde pour le SBA. Lorsque le pool frontal est migré vers Skype entreprise Server 2019, l’interface SBA doit être désassociée du pool frontal lors de la mise à niveau du pool. Une fois que le regroupement a été déplacé vers Skype entreprise Server 2019, il est possible d’associer de nouveau l’SBA au pool frontal mis à niveau. Cela implique la suppression de l’SBA de la topologie héritée dans le générateur de topologie, puis l’ajout de l’SBA à la topologie 2019 de Skype entreprise Server. Les utilisateurs hébergés sur l’ancien SBA doivent d’abord être déplacés vers un autre pool frontal avant de supprimer l’SBA de la topologie. Une fois que le SBA a été ajouté à la topologie 2019 de Skype entreprise Server, il peut être ramené à l’SBA. Ces étapes sont décrites ci-dessous:
  
1. Déplacez les utilisateurs de succursales hébergés de l’ancien SBA vers un autre pool frontal.
    
2. Supprimez SBA de la topologie héritée pour déconnecter le pool frontal existant en tant qu’Bureau d’enregistrement de sauvegarde.
    
3. Ajoutez SBA à la topologie 2019 de Skype entreprise Server et configurez cette nouvelle réserve frontale en tant qu’Bureau d’enregistrement de sauvegarde. 
    
4. Déplacez les utilisateurs de la succursale vers le nouveau Skype entreprise Server 2019 SBA.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Ajouter un site de filiale hérité de SBA à votre topologie

1. Ouvrez le **Générateur de topologie**.
    
2. Dans le volet gauche, cliquez avec le bouton droit sur **sites**de succursales, puis cliquez sur **nouveau site de succursale**.
    
3. Dans la boîte de dialogue **définir un nouveau site de succursale** , cliquez sur **nom**, puis tapez le nom du site de la succursale.
    
4. Facultatif Cliquez sur **Description**, puis tapez une description significative pour le site de la succursale.
    
5. Cliquez sur **Suivant**.
    
6. Facultatif Dans la boîte de dialogue **définir un nouveau site de succursale** suivante, effectuez l’une des opérations suivantes: 
    
    1. Cliquez sur **City**, puis tapez le nom de la ville dans laquelle se trouve le site de la succursale.
    
    2. Cliquez sur **état/région**, puis tapez le nom de l’État ou de la région où se trouve le site de la succursale.
    
    3. Cliquez sur **indicatif du pays**, puis tapez le code d’appel à deux chiffres correspondant au pays/la région où se trouve le site de la succursale.
    
7. Cliquez sur **suivant**, puis, si vous utilisez une application ou un serveur Survivable sur ce site, désactivez la case à cocher **ouvrir le nouvel Assistant survie lorsque cet Assistant se ferme** . Cliquez sur **Terminer**.
    
8. Pour associer l’ancien SBA au pool frontal 2019 de Skype entreprise Server, procédez comme suit:
    
    1. Développez le site de succursale qui a été créé. 
    
    2. Cliquez avec le bouton droit sur version héritée, puis cliquez sur **nouveau**.
    
    3. Cliquez sur l' **application branchement Survivable**.
    
9. Suivez les instructions de l’Assistant qui s’ouvre. Pour plus d’informations sur les éléments de l’Assistant, voir    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Une unité de branchement Survivable ne peut être associée qu’à un magasin d’analyse. 
  
10. Si vous n’utilisez pas d’appareil ou serveur de succursales survivant sur ce site, désactivez la case à cocher **ouvrir le nouvel Assistant survie lorsque cet Assistant se ferme** , puis cliquez sur **Terminer**.
    
11. Répétez les étapes précédentes pour chaque site de succursale que vous voulez ajouter à la topologie.
    

