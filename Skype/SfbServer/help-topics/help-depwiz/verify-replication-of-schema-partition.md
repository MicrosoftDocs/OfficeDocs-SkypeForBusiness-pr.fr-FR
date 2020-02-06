---
title: Vérifier la réplication de la partition du schéma
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Pour vérifier que l’extension de schéma a bien été répliquée dans votre forêt services de domaine Active Directory (AD FS), procédez comme suit :'
ms.openlocfilehash: f2e8c181f01e841ebc6b251d8215a8d448db0b04
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41823268"
---
# <a name="verify-replication-of-schema-partition"></a>Vérifier la réplication de la partition du schéma
 
Pour vérifier que l’extension de schéma a bien été répliquée dans votre forêt services de domaine Active Directory (AD FS), procédez comme suit :
  
1. Ouvrez une session sur un contrôleur de domaine (autre que le contrôleur de domaine qui contient le rôle de maître de schéma) dans votre forêt services de domaine Active Directory (AD DS), où les extensions de schéma étaient appliquées en tant que membre du groupe administrateurs d’entreprise.
    
2. Ouvrez ADSI Edit : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **modification ADSI**.
    
    > [!TIP]
    > Vous pouvez également cliquer sur **Démarrer**, puis sur **exécuter**, taper **adsied. msc** pour démarrer ADSI Edit.
  
3. Dans l’arborescence Microsoft Management Console (MMC), si ce n’est pas déjà fait, cliquez sur ADSI Edit.
    
4. Dans le menu **Action**, cliquez sur **Connexion**.
    
5. Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.
    
6. Sous le conteneur de schéma, recherchez CN=ms-RTC-SIP-SchemaVersion. Si cet objet existe et que la valeur de l’attribut **rangeUpper** est 1150 et que la valeur de l’attribut **rangeLower** est 3, le schéma a été correctement mis à jour et répliqué. Si cet objet n’existe pas ou si les valeurs des attributs **rangeUpper** et **rangeLower** ne sont pas spécifiées, le schéma n’a pas été modifié ou n’a pas été répliqué.
    
> [!NOTE]
> Si votre vérification de la réplication du schéma ne montre pas encore de réussite, attendez environ 15 minutes avant de procéder à la vérification. La réplication Active Directory est basée sur un modèle de cohérence faible et une latence de réplication peut se produire en fonction de plusieurs facteurs du serveur et de l’infrastructure. 
  

