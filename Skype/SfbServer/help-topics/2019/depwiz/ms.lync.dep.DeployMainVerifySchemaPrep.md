---
title: Vérifier la réplication de la partition du schéma
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainVerifySchemaPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 0357f230-6d0c-41f1-942c-e14f76e55d31
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour vérifier que l’extension de schéma a bien été répliquée dans votre forêt des services de domaine Active Directory, faites les choses suivantes :'
ms.openlocfilehash: 9da233460dd20548acd36bd90ef699359c77e4144eaea80576e1209df6a5c7fb
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54300220"
---
# <a name="verify-replication-of-schema-partition"></a>Vérifier la réplication de la partition du schéma
 
Pour vérifier que l’extension de schéma a bien été répliquée dans votre forêt des services de domaine Active Directory, faites les choses suivantes :
  
1. Log on to a domain controller (other than the domain controller that holds the schema master role) in your Active Directory Domain Services forest, where the schema extensions were applied as a member of the Enterprise Admins group.
    
2. Ouvrez l’éditeur ADSI : cliquez sur **Démarrer**, sur **Outils d’administration**, puis sur **Modification ADSI**.
    
    > [!TIP]
    > Vous pouvez également cliquer sur **Démarrer**, puis sur **Exécuter**, et taper **adsiedit.msc** pour démarrer l’éditeur ADSI.
  
3. Dans l’arborescence de la console MMC, s’il n'est pas encore sélectionné, cliquez sur Modification ADSI.
    
4. Dans le menu **Action**, cliquez sur **Se connecter à**.
    
5. Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.
    
6. Sous le conteneur de schéma, recherchez CN=ms-RTC-SIP-SchemaVersion. Si cet objet existe et si la valeur de l’attribut **rangeUpper** est 1150 et si la valeur de l’attribut **rangeLower** est 3, cela signifie que le schéma a été mis à jour et répliqué avec succès. Si cet objet n’existe pas ou si la valeur des attributs **rangeUpper** et **rangeLower** n’est pas spécifiée, cela signifie que le schéma n’a pas été modifié ou n’a pas été répliqué.
    
> [!NOTE]
> Si, lorsque vous recherchez la réplication du schéma, celle-ci n’apparaît pas comme ayant abouti, patientez environ 15 minutes avant de réessayer. La réplication Active Directory est basée sur un modèle de cohérence souple et une certaine latence de réplication peut se produire, en fonction d’un certain nombre de facteurs dans le serveur et l’infrastructure. 
  

