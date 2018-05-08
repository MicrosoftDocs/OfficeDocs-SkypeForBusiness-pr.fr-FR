---
title: Publication des modifications en attente de la configuration du routage des communications vocales dans Skype Entreprise 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Résumé : Apprenez à vérifier, publier ou annuler les modifications de configuration routage des communications vocales dans Skype pour Business Server 2015 à l’aide de la Skype pour le panneau de configuration serveur Business.'
ms.openlocfilehash: 34da8d44a778d5a469cc7069e0024dd3b43517ab
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business-2015"></a>Publication des modifications en attente de la configuration du routage des communications vocales dans Skype Entreprise 2015
 
**Résumé :** Découvrez comment passez en revue, publier ou annuler les modifications de configuration routage des communications vocales dans Skype pour Business Server 2015 à l’aide de la Skype pour le panneau de configuration serveur Business.
  
Après avoir modifié les paramètres de configuration dans les pages du groupe **Routage des communications vocales**, effectuez cette procédure pour consulter, publier ou annuler les modifications en attente.
  
> [!IMPORTANT]
> Vérifiez qu’un seul utilisateur à la fois modifie les paramètres de configuration du routage des communications vocales. 
  
> [!NOTE]
> Toutes les modifications en attente doivent être publiées en même temps en exécutant la commande **Tout valider**. Vous ne pouvez pas sélectionner les modifications en attente que vous voulez publier. Avant de publier les modifications en attente, exécutez la commande **Vérifier les modifications non validées** et annulez les modifications de configuration que vous ne voulez pas publier.
  
> [!NOTE]
> Si vous quittez les pages du groupe **Routage des communications vocales** avant d’avoir validé les modifications en attente, toutes les modifications en attente seront perdues. Cependant, vous pouvez exporter la configuration active (y compris les modifications en attente) vers un fichier de configuration des communications vocales, puis importer et publier la configuration mise à jour. Pour plus d’informations, voir [exporter ou importer un fichier de configuration vocale itinéraire dans Skype pour Business 2015](voice-route-configuration-import-export.md). 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Pour consulter, publier ou annuler les modifications de la configuration du routage des communications vocales

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.
    
2. Ouvrez le panneau de configuration serveur Business Skype.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Effectuez les modifications souhaitées au niveau de la configuration dans chacune des pages du groupe **Routage des communications vocales**.
    
5. Pour consulter les modifications en attente sans les publier, sélectionnez **Vérifier les modifications non validées** dans le menu **Valider**.
    
6. Si vous souhaitez annuler l’une des modifications en attente, effectuez l’une des opérations suivantes :
    
   - Sélectionnez **Annuler toutes les modifications non validées** dans le menu **Valider**.
    
   - Accédez à l’onglet de la page **Routage des communications vocales** qui contient les modifications en attente que vous souhaitez annuler, cliquez sur **Valider**, puis sur **Annuler les modifications sélectionnées**.
    
7. Une fois que vous avez vérifié toutes les modifications en attente et annulé celles que vous ne souhaitez pas publier, cliquez sur **Valider**, puis sur **Tout valider**.
    
8. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés** qui contient la liste de toutes les modifications en attente, cliquez sur **OK**. 
    
    Skype pour le panneau de configuration serveur Business a validé les modifications, le message **publié avec succès la configuration de routage voix** s’affiche.
    

