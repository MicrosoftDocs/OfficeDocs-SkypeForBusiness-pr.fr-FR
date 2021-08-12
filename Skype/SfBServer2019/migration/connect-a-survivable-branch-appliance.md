---
title: Connexion d’une Survivable Branch Appliance
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Chaque Survivable Branch Appliance (SBA) est associé à un pool frontal qui sert de bureau d’enregistrement de sauvegarde pour le SBA. Lorsque le pool frontal est migré vers Skype Entreprise Server 2019, l’SBA doit être dissocié du pool frontal pendant la mise à niveau du pool. Une fois que le pool a été migré vers Skype Entreprise Server 2019, il peut être réassocié au pool frontal mis à niveau. Cela implique la suppression du SBA de la topologie héritée dans le Générateur de topologie, puis l’ajout du SBA à la topologie Skype Entreprise Server 2019. Les utilisateurs d’un SBA hérité doivent d’abord être déplacés vers un autre pool frontal avant de supprimer le SBA de la topologie. Une fois que le SBA est ajouté à la topologie Skype Entreprise Server 2019, ces utilisateurs peuvent ensuite être déplacés vers le SBA. Voici un récapitulatif de ces étapes :'
ms.openlocfilehash: 4977868c45b274adea514d84e251f682da02cc8ee486a5a182d984ee652f3ae2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54313872"
---
# <a name="connect-a-survivable-branch-appliance"></a>Connexion d’une Survivable Branch Appliance

Chaque Survivable Branch Appliance (SBA) est associé à un pool frontal qui sert de bureau d’enregistrement de sauvegarde pour le SBA. Lorsque le pool frontal est migré vers Skype Entreprise Server 2019, le SBA doit être dissocié du pool frontal pendant la mise à niveau du pool. Une fois le pool migré vers Skype Entreprise Server 2019, le SBA peut être ré-associé au pool frontal mis à niveau. Cela implique la suppression du SBA de la topologie héritée dans le Générateur de topologie, puis l’ajout du SBA à la topologie Skype Entreprise Server 2019. Les utilisateurs d’un SBA hérité doivent d’abord être déplacés vers un autre pool frontal avant de supprimer le SBA de la topologie. Une fois le SBA ajouté à la topologie Skype Entreprise Server 2019, ces utilisateurs peuvent être rebassé vers le SBA. Voici un récapitulatif de ces étapes :
  
1. Déplacez les utilisateurs de succursales sur le SBA hérité vers un autre pool frontal.
    
2. Supprimez le SBA de la topologie héritée pour déconnecter le pool frontal existant en tant que bureau d’enregistrement de sauvegarde.
    
3. Ajoutez SBA à la topologie Skype Entreprise Server 2019 et configurez ce nouveau pool frontal en tant que bureau d’enregistrement de sauvegarde. 
    
4. Déplacez les utilisateurs de succursale vers le nouveau SBA Skype Entreprise Server 2019.
    
### <a name="add-legacy-sba-branch-site-to-your-topology"></a>Ajouter un site de succursale SBA hérité à votre topologie

1. Ouvrez le **Générateur de topologie**.
    
2. Dans le volet gauche, cliquez avec le bouton droit sur **Sites de succursale,** puis cliquez sur **Nouveau site de succursale.**
    
3. Dans la boîte de dialogue **Définir un nouveau site de succursale**, cliquez sur **Nom**, puis tapez le nom du site de succursale.
    
4. (Facultatif) Cliquez sur **Description**, puis tapez une description explicite pour le site de succursale.
    
5. Cliquez sur **Suivant**.
    
6. (Facultatif) Dans la boîte de dialogue **Définir un nouveau site de succursale** qui suit, effectuez l’une des opérations suivantes : 
    
    1. Cliquez sur **Ville**, puis tapez le nom de la ville dans laquelle se trouve le site de succursale.
    
    2. Cliquez sur **Dép./Région**, puis tapez le nom du département ou de la région où se trouve le site de succursale.
    
    3. Cliquez sur **Code du pays**, puis tapez le code d’appel à deux chiffres du pays ou de la région du site de succursale.
    
7. Cliquez **sur** Suivant, puis, si vous utilisez un Survivable Branch Appliance ou un serveur Survivable Branch Server sur ce site, n’oubliez pas d’ouvrir l’Assistant Nouveau **Survivable Lorsque** cet Assistant ferme la case. Cliquez sur **Terminer**.
    
8. Pour associer l’ancien SBA au pool frontal Skype Entreprise Server 2019 :
    
    1. Développez le site de succursale créé. 
    
    2. Cliquez avec le bouton droit sur la version héritée, puis cliquez sur **Nouveau.**
    
    3. Cliquez **sur Survivable Branch Appliance**.
    
9. Suivez les instructions de l’Assistant qui s’ouvre. Pour plus d’informations sur les éléments de l’Assistant, voir    
   <!-- [Define a Survivable Branch Appliance or Server in Lync 2013](/previous-versions/office/lync-server-2013/lync-server-2013-define-a-survivable-branch-appliance-or-server). -->
   <!-- The above link points to un-rebranded 2013 content we will need to discuss rebrand or bring forward -->
    
    > [!NOTE]
    > Un Survivable Branch Appliance ne peut être associé qu’à un magasin de surveillance. 
  
10. Si vous n’utilisez pas de SBA ou de serveur sur ce site, désactivez la case à cocher **Ouvrir l’Assistant Nouveau Survivable Branch Appliance à la fermeture de cet Assistant**, puis cliquez sur **Terminer**.
    
11. Répétez les étapes précédentes pour chaque site de succursale que vous voulez ajouter à la topologie.
