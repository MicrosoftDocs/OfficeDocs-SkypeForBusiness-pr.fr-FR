---
title: Se connecter à un serveur Survivable Branch Appliance
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Chaque serveur Survivable Branch Appliance (SBA) est associé à un pool frontal qui sert à un serveur d’inscriptions de sauvegarde pour le SBA. Lorsque le pool est migré vers Skype pour Business Server 2019, le SBA serveur frontal doit être dissocié du pool frontal alors que le pool est mis à niveau, une fois que le pool a été migré vers Skype pour Business Server 2019, le SBA peut être nouveau associé à la mise à niveau E avant pool ND. Cela consiste à supprimer le SBA à partir de la topologie héritée dans le Générateur de topologie et en ajoutant le SBA à la Skype pour Business Server 2019 topologie. Les utilisateurs hébergés sur hérité que SBA doit tout d’abord être déplacé vers un autre pool frontal avant de supprimer le SBA de la topologie. Une fois le SBA est ajouté à la Skype pour topologie Business Server 2019, ces utilisateurs peuvent ensuite revenir au SBA. Ces étapes sont résumées ci-dessous :'
ms.openlocfilehash: 6de2b8c228ef9e65f57b70451ac33350a2d8a456
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25030580"
---
# <a name="connect-a-survivable-branch-appliance"></a>Se connecter à un serveur Survivable Branch Appliance

Chaque serveur Survivable Branch Appliance (SBA) est associé à un pool frontal qui sert à un serveur d’inscriptions de sauvegarde pour le SBA. Lorsque le pool frontal est migré vers Skype pour Business Server 2019, SBA doit être dissocié le pool frontal alors que le pool est mis à niveau. Une fois que le pool a été migré vers Skype pour Business Server 2019, le SBA peut être nouveau associé au pool frontal mis à niveau. Cela consiste à supprimer le SBA à partir de la topologie héritée dans le Générateur de topologie et en ajoutant le SBA à la Skype pour Business Server 2019 topologie. Les utilisateurs hébergés sur hérité que SBA doit tout d’abord être déplacé vers un autre pool frontal avant de supprimer le SBA de la topologie. Après que le SBA est ajouté à la Skype pour topologie Business Server 2019, ces utilisateurs peuvent être déplacés vers le SBA. Ces étapes sont résumées ci-dessous :
  
1. Déplacez les utilisateurs de succursale hébergement sur le SBA hérité vers un autre pool frontal.
    
2. Supprimez le SBA de la topologie héritée pour déconnecter le pool frontal existant en tant qu’un serveur d’inscriptions de sauvegarde.
    
3. Ajouter le SBA à la Skype pour topologie Business Server 2019 et configurez ce nouveau pool frontal en tant que le serveur d’inscriptions de sauvegarde. 
    
4. Déplacer les utilisateurs de succursale vers le nouveau Skype pour Business Server 2019 SBA.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Ajouter un site de succursale SBA hérité à votre topologie

1. Ouvrez **le Générateur de topologie**.
    
2. Dans le volet gauche, cliquez sur **sites de succursale**, puis cliquez sur **Nouveau Site de succursale**.
    
3. Dans la boîte de dialogue **Définir un nouveau Site de succursale** , cliquez sur **nom**, puis tapez le nom du site de succursale.
    
4. (Facultatif) Cliquez sur **Description**, puis tapez une description explicite pour le site de succursale.
    
5. Cliquez sur **Suivant**.
    
6. (Facultatif) Dans la boîte de dialogue **Définir un nouveau Site de succursale** suivante, effectuez l’une des options suivantes : 
    
    1. Cliquez sur **Ville**, puis tapez le nom de la ville dans laquelle se trouve le site de succursale.
    
    2. Cliquez sur Dép./région ****, puis tapez le nom de l’état ou la région dans lequel se trouve le site de succursale.
    
    3. Cliquez sur **Code du pays**, puis tapez le code appelant à deux chiffres pour le pays/la région dans laquelle se trouve le site de succursale.
    
7. Cliquez sur **suivant**, puis, si vous utilisez un serveur Survivable Branch Appliance ou un serveur de ce site, veillez à désactiver la case à cocher **Ouvrir l’Assistant Survivable nouvelle fermeture de cet Assistant** . Cliquez sur **Terminer**.
    
8. Pour associer le SBA hérité pour la Skype pour Business Server 2019 un pool frontal :
    
    1. Développez le site de succursale qui a été créé. 
    
    2. Avec le bouton droit sur la version héritée, puis cliquez sur **Nouveau**.
    
    3. Cliquez sur **Survivable Branch Appliance**.
    
9. Suivez les instructions de l’Assistant qui s’ouvre. Pour plus d’informations sur les éléments de l’Assistant, consultez    
<!-- [Define a Survivable Branch Appliance or Server in Lync 2013](https://technet.microsoft.com/en-us/library/gg398280(v=ocs.15).aspx). -->
 <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Un Survivable Branch Appliance peut uniquement être associé à un magasin de surveillance. 
  
10. Si vous n’utilisez pas un Survivable Branch Appliance ou un serveur de ce site, désactivez la case à cocher **Ouvrir l’Assistant Survivable nouvelle fermeture de cet Assistant** , puis cliquez sur **Terminer**.
    
11. Répétez les étapes précédentes pour chaque site de succursale que vous souhaitez ajouter à la topologie.
    

