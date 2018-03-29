---
title: Assistant Certificat
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
description: Pour demander, affecter, supprimer ou afficher des certificats, vous utilisez l’Assistant certificat. Vous devez être connecté en tant que membre du groupe RTCUniversalServerAdmins. Pour demander un certificat à une autorité de certification publique, il n’est pas nécessaire que vous soyez membre d’autres groupes. Pour demander un certificat à partir de l’infrastructure à clé publique de votre entreprise (PKI), vous devez confirmer que supplémentaires — le cas échéant, vous devrez les appartenances de groupe. Au cours de la tâche de la demande, vous pouvez entrer des informations d’identification alternatives qui seront utilisées pour demander que le certificat à partir de votre infrastructure à clé publique de l’autorité de certification.
ms.openlocfilehash: d700a6cae510bbc12ed2e37c9c3df166d2704269
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="certificate-wizard"></a>Assistant Certificat
 
Pour **Demander**, **Assigner**, **Supprimer** ou **Afficher** des certificats, utilisez l’Assistant Certificat. Vous devez être connecté en tant que membre du groupe RTCUniversalServerAdmins. Pour demander un certificat à une autorité de certification publique, il n’est pas nécessaire que vous soyez membre d’autres groupes. Pour demander un certificat à partir de l’infrastructure à clé publique de votre entreprise (PKI), vous devez confirmer que supplémentaires — le cas échéant, vous devrez les appartenances de groupe. Au cours de la tâche de la demande, vous pouvez entrer des informations d’identification alternatives qui seront utilisées pour demander que le certificat à partir de votre infrastructure à clé publique de l’autorité de certification.
  
Pour demander un nouveau certificat, cliquez sur **Demander**.
  
Pour assigner un certificat qui n’a pas encore été assigné, cliquez sur **Assigner**.
  
Pour supprimer un certificat que vous avez précédemment assigné, cliquez sur **Supprimer**.
  
> [!NOTE]
> Le bouton **Supprimer** est disponible uniquement si un certificat a été précédemment assigné. Si le bouton **Supprimer** n’est pas disponible (grisé), cela signifie qu’aucun certificat n’a été assigné.
  
Pour afficher un certificat assigné, cliquez sur **Afficher**.
  
> [!NOTE]
> Le bouton **Afficher** est disponible uniquement si un certificat a été précédemment assigné. Si le bouton **Afficher** est grisé, cela signifie qu’aucun certificat n’a été assigné.
  
Pour actualiser l’écran d’assignation du certificat actuel, cliquez sur **Actualiser**.
  
Pour importer un certificat qui n’est pas présent dans le magasin de certificats, cliquez sur **Importer un certificat**.
  
> [!NOTE]
> L’option **Importer un certificat** est généralement utilisée pour traiter un certificat qui est reçu par le biais d’un processus autre qu’une demande de l’Assistant Certificat. Par exemple, l’administrateur de votre infrastructure à clé publique crée un certificat et vous permet d’y accéder. **Importer un certificat** à importer le certificat dans le certificat de l’ordinateur stocker et le rendre disponible à Skype pour Business Server à affecter.
  
Pour terminer le processus de demande de certificat auprès d’une autorité de certification de votre organisation qui nécessite l’approbation de l’administrateur de l’autorité de certification, cliquez sur **Traiter une demande en attente**. La demande de certificat affiche un statut en attente, ainsi que le numéro d’identification de la demande en attente. Pour poursuivre le traitement d’un certificat dont le statut est en attente, cliquez sur **Actualiser** pour activer le bouton **Traiter une demande en attente**. Le bouton **Traiter une demande en attente** n’est plus inaccessible (grisé). Vous pouvez ensuite essayer de récupérer la demande en attente, mais le statut de la demande restera en attente tant que le certificat n’aura pas été émis ou rejeté par l’administrateur de l’autorité de certification. Le bouton est inaccessible si aucune demande en attente valide n’a été créée par l’Assistant Certificat.
  

