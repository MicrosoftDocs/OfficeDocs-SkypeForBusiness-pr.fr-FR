---
title: Vérification de la réplication de la Partition de schéma
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
description: 'Pour vérifier que l’extension de schéma ont été correctement répliqués dans votre forêt des Services de domaine Active Directory, effectuez les opérations suivantes :'
ms.openlocfilehash: a5628e369ffc796affe9984cef8ecb1ba044ec8a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="verify-replication-of-schema-partition"></a>Vérification de la réplication de la Partition de schéma
 
Pour vérifier que l’extension de schéma ont été correctement répliqués dans votre forêt des Services de domaine Active Directory, effectuez les opérations suivantes :
  
1. Ouvrez une session sur un contrôleur de domaine (autre que le contrôleur de domaine qui détient le rôle de maître de schéma) dans votre forêt des Services de domaine Active Directory, où les extensions de schéma ont été appliquées en tant que membre du groupe Administrateurs de l’entreprise.
    
2. Ouvrez ADSI Edit : Cliquez sur **Démarrer**, sur **Outils d’administration**, puis cliquez sur **ADSI Edit**.
    
    > [!TIP]
    > Sinon, cliquez sur **Démarrer**, puis sur **exécuter**, type **adsiedit.msc** pour démarrer l’utilitaire de modification ADSI.
  
3. Dans l’arborescence de la Console de gestion Microsoft (MMC), s’il n’est pas déjà sélectionné, cliquez sur ADSI Edit.
    
4. Dans le menu **Action**, cliquez sur **Connexion**.
    
5. Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.
    
6. Sous le conteneur schéma, recherchez CN = ms-RTC-SIP-version de schéma. Si cet objet existe et la valeur de l’attribut **rangeUpper** est 1150 et la valeur de l’attribut **rangeLower** a la valeur 3, puis le schéma a été correctement mis à jour et répliqué. Si cet objet n’existe pas ou si les valeurs des attributs **rangeUpper** et **rangeLower** ne sont pas spécifiés, puis le schéma n’a pas été modifié ou n’a pas répliqué.
    
> [!NOTE]
> Si votre contrôle de la réplication du schéma ne s’affiche pas encore une réplication réussie, attendez 15 minutes environ, puis vérifiez à nouveau. La réplication Active Directory est basée sur un modèle de cohérence et une latence de réplication peut se produire, basée sur un certain nombre de facteurs dans le serveur et l’infrastructure. 
  

