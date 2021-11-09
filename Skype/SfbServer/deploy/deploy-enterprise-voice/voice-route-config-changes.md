---
title: Publier les modifications en attente de la configuration du routage des Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: ff941d0b-fb4b-47d2-b866-6d990ac66b81
description: 'Résumé : Découvrez comment examiner, publier ou annuler les modifications apportées à la configuration du routage des Skype Entreprise Server à l’aide du Skype Entreprise Server de configuration.'
ms.openlocfilehash: e0ffa60557623eb217f7f43a61cad7b2e0923c77
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856281"
---
# <a name="publish-pending-changes-to-the-voice-routing-configuration-in-skype-for-business"></a>Publier les modifications en attente de la configuration du routage des Skype Entreprise
 
**Résumé :** Découvrez comment examiner, publier ou annuler les modifications apportées à la configuration du routage des Skype Entreprise Server à l’aide du Panneau Skype Entreprise Server de configuration.
  
Après avoir modifié les paramètres de configuration dans les pages du groupe **Routage des communications vocales**, effectuez cette procédure pour passer en revue, publier ou annuler les modifications en attente.
  
> [!IMPORTANT]
> Vérifiez qu’un seul utilisateur à la fois modifie les paramètres de configuration du routage des communications vocales. 
  
> [!NOTE]
> Toutes les modifications en attente doivent être publiées en même temps en exécutant la commande **Valider tout**. Vous ne pouvez pas sélectionner les modifications en attente que vous voulez publier. Avant de publier les modifications en attente, exécutez la commande **Vérifier les modifications non validées** et annulez les modifications de configuration que vous ne voulez pas publier.
  
> [!NOTE]
> Si vous quittez les pages du groupe **Routage des communications vocales** avant d’avoir validé les modifications en attente, toutes les modifications en attente seront perdues. Toutefois, vous pouvez exporter la configuration en cours (y compris les modifications en attente) vers un fichier de configuration des communications vocales, puis importer et publier la configuration mise à jour. Pour plus d’informations, voir Exporter ou importer un fichier de configuration de [l’itinéraire des](voice-route-configuration-import-export.md)Skype Entreprise . 
  
### <a name="to-review-publish-or-cancel-voice-routing-configuration-changes"></a>Pour passer en revue, publier ou annuler les modifications de la configuration du routage des communications vocales

1. Connectez-vous à l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins, ou en tant que membre du rôle d’administrateur **CsVoiceAdministrator**, **CsServerAdministrator** ou **CsAdministrator**.
    
2. Ouvrez Skype Entreprise Server panneau de contrôle.
    
3. Dans la barre de navigation de gauche, cliquez sur **Routage des communications vocales**.
    
4. Effectuez les modifications souhaitées au niveau de la configuration sur chacune des pages du groupe **Routage des communications vocales**.
    
5. Pour passer en revue les modifications en attente sans les publier, sélectionnez **Vérifier les modifications non validées** dans le menu **Valider**.
    
6. Si vous souhaitez annuler l’une des modifications en attente, effectuez l’une des opérations suivantes :
    
   - Sélectionnez **Annuler toutes les modifications non validées** dans le menu **Valider**.
    
   - Accédez à l’onglet de la page **Routage des communications vocales** où se trouvent les modifications en attente que vous souhaitez annuler, cliquez sur **Valider**, puis sur **Annuler les modifications sélectionnées**.
    
7. Une fois que vous avez passé en revue toutes les modifications en attente et annulé celles que vous ne souhaitez pas publier, cliquez sur **Valider**, puis sur **Valider tout**.
    
8. Dans la boîte de dialogue **Paramètres de configuration de la voix non validés** qui affiche la liste de toutes les modifications en attente, cliquez sur **OK**. 
    
    Lorsque Skype Entreprise Server panneau de configuration a engagé les modifications, le message de configuration du **routage** des messages vocaux publié avec succès s’affiche.
    

