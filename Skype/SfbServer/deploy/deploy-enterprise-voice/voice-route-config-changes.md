---
title: Les modifications en attente apportées à la configuration de l’acheminement vocal dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Résumé : Découvrez comment réviser, publier ou annuler les modifications de configuration de l’acheminement vocal dans Skype entreprise Server à l’aide du panneau de configuration Skype entreprise Server.'
ms.openlocfilehash: 12cf80c2a14d3bad532aaf21a942536f44537300
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766957"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>Les modifications en attente apportées à la configuration de l’acheminement vocal dans Skype entreprise
 
**Résumé :** Découvrez comment réviser, publier ou annuler les modifications de configuration de l’acheminement vocal dans Skype entreprise Server à l’aide du panneau de configuration Skype entreprise Server.
  
Après avoir modifié les paramètres de configuration dans les pages du groupe **Routage des communications vocales**, effectuez cette procédure pour consulter, publier ou annuler les modifications en attente.
  
> [!IMPORTANT]
> Vérifiez qu’un seul utilisateur à la fois modifie les paramètres de configuration du routage des communications vocales. 
  
> [!NOTE]
> Toutes les modifications en attente doivent être publiées en même temps en exécutant la commande **Tout valider**. Vous ne pouvez pas sélectionner les modifications en attente que vous voulez publier. Avant de publier les modifications en attente, exécutez la commande **Vérifier les modifications non validées** et annulez les modifications de configuration que vous ne voulez pas publier.
  
> [!NOTE]
> Si vous quittez les pages du groupe **Routage des communications vocales** avant d’avoir validé les modifications en attente, toutes les modifications en attente seront perdues. Cependant, vous pouvez exporter la configuration active (y compris les modifications en attente) vers un fichier de configuration des communications vocales, puis importer et publier la configuration mise à jour. Pour plus d’informations, reportez-vous à [exporter ou importer un fichier de configuration d’itinéraires vocaux dans Skype entreprise](voice-route-configuration-import-export.md). 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Pour consulter, publier ou annuler les modifications de la configuration du routage des communications vocales

1. Ouvrez une session sur l’ordinateur en tant que membre du groupe **RTCUniversalServerAdmins** ou membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou CsAdministrator.
    
2. Ouvrez le panneau de configuration Skype entreprise Server.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Effectuez les modifications souhaitées au niveau de la configuration dans chacune des pages du groupe **Routage des communications vocales**.
    
5. Pour consulter les modifications en attente sans les publier, sélectionnez **Vérifier les modifications non validées** dans le menu **Valider**.
    
6. Si vous souhaitez annuler l’une des modifications en attente, effectuez l’une des opérations suivantes :
    
   - Sélectionnez **Annuler toutes les modifications non validées** dans le menu **Valider**.
    
   - Accédez à l’onglet de la page **Routage des communications vocales** qui contient les modifications en attente que vous souhaitez annuler, cliquez sur **Valider**, puis sur **Annuler les modifications sélectionnées**.
    
7. Une fois que vous avez vérifié toutes les modifications en attente et annulé celles que vous ne souhaitez pas publier, cliquez sur **Valider**, puis sur **Tout valider**.
    
8. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés** qui contient la liste de toutes les modifications en attente, cliquez sur **OK**. 
    
    Lorsque le panneau de configuration Skype entreprise Server a validé les modifications, le message de configuration de l’acheminement des messages a **été correctement publié** s’affiche.
    

