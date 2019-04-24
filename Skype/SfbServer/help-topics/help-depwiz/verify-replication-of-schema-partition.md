---
title: Vérifier la réplication de la partition du schéma
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Pour vérifier que l’extension de schéma a été correctement répliquée dans votre forêt Active Directory Domain Services, procédez comme suit :'
ms.openlocfilehash: 38d5983623c837e931274deef7581dd1567fc492
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32234858"
---
# <a name="verify-replication-of-schema-partition"></a>Vérifier la réplication de la partition du schéma
 
Pour vérifier que l’extension de schéma a été correctement répliquée dans votre forêt Active Directory Domain Services, procédez comme suit :
  
1. Ouvrez une session un contrôleur de domaine (autre que le contrôleur de domaine qui détient le rôle de contrôleur de schéma) dans votre forêt Active Directory Domain Services, où les extensions de schéma ont été appliquées en tant que membre du groupe Administrateurs de l’entreprise.
    
2. Open éditeur ADSI : Cliquez sur **Démarrer**, sur **Outils d’administration**, puis cliquez sur **Modification ADSI**.
    
    > [!TIP]
    > Autrement, cliquez sur **Démarrer**, puis cliquez sur **exécuter**, type **adsiedit.msc** pour démarrer l’éditeur ADSI.
  
3. Dans l’arborescence de Microsoft Management Console (MMC), s’il n’est pas déjà sélectionné, cliquez sur Modification ADSI.
    
4. Dans le menu **Action**, cliquez sur **Connexion**.
    
5. Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.
    
6. Sous le conteneur de schéma, recherchez CN=ms-RTC-SIP-SchemaVersion. Si cet objet existe et la valeur de l’attribut **rangeUpper** est 1150 et la valeur de l’attribut **rangeLower** est 3, puis le schéma a été correctement mis à jour et répliqué. Si cet objet n’existe pas ou si les valeurs des attributs **rangeUpper** et **rangeLower** ne sont pas en tant que spécifié, puis le schéma n’a pas été modifié ou n’a pas été répliqué.
    
> [!NOTE]
> Si votre contrôle de la réplication du schéma n’affiche pas encore une réplication réussie, attendez environ 15 minutes, puis vérifiez à nouveau. La réplication Active Directory est basée sur un modèle de cohérence et une latence de réplication peut se produire, basée sur un certain nombre de facteurs dans le serveur et l’infrastructure. 
  

