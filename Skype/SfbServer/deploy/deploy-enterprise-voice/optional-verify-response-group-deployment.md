---
title: (Facultatif) Vérifier le déploiement de Response Group dans Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 202ca4ab-8e6d-44a4-b7c8-071133074feb
description: Vérifiez la réussite de votre déploiement Response Group, Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: 8e9820a68e06c3cf9ec583c9aad2e86708583ac9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60753481"
---
# <a name="optional-verify-response-group-deployment-in-skype-for-business"></a>(Facultatif) Vérifier le déploiement de Response Group dans Skype Entreprise
 
Vérifiez la réussite de votre déploiement Response Group, Skype Entreprise Server Voix Entreprise.
  
Après avoir configuré Response Group, vous devez vérifier la configuration pour vous assurer que vos groupes Response Group fonctionnent comme prévu. Au minimum, vérifiez les scénarios suivants en vous basant sur les types d’utilisateur indiqués ci-dessous :
  
 **Utilisateurs**
  
- Utilisateur qui est homed on Skype Entreprise
    
- Utilisateur externe qui utilise le réseau téléphonique commuté (PSTN) public
    
- Agent qui est homed on Skype Entreprise
    
  **Scenarios**
  
- L’Skype Entreprise appelle le groupe Response Group.
    
- L’utilisateur externe appelle le service Response Group.
    
- Un utilisateur appelle le service Response Group alors que l’agent traite un autre appel. L’appel de l’utilisateur est alors transmis à la file d’attente.

    > [!NOTE]
    > Si le groupe Response Group ne fonctionne pas comme prévu, consultez le lien suivant : https://support.office.com/article/troubleshooting-for-response-groups-ca72d8f8-4054-4974-b832-4f173611bd89
    

