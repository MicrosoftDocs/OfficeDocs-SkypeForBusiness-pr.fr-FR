---
title: Assistant Certificat
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertsMain
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 6ab661d7-5741-4cad-bbe4-62cf862ded85
description: Pour Demander, Assigner, Supprimer ou Afficher des certificats, utilisez l’Assistant Certificat. Vous devez être connecté en tant que membre du groupe RTCUniversalServerAdmins. Pour demander un certificat à partir d’une autorité de certification publique, il n’est pas nécessaire que vous soyez membre d’autres groupes. Pour demander un certificat auprès de l’infrastructure à clé publique (PKI) de votre organisation, vous devez confirmer les appartenances de groupe supplémentaires, le cas besoin. Au cours de la tâche Demander, vous pouvez entrer d’autres informations d’identification qui seront utilisées pour demander le certificat auprès de l’ac émettrice de votre PKI.
ms.openlocfilehash: b79d04b3fa4d5579b586b4c37cd49d48740523c5
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393026"
---
# <a name="certificate-wizard"></a>Assistant Certificat
 
Pour **Demander**, **Assigner**, **Supprimer** ou **Afficher** des certificats, utilisez l’Assistant Certificat. Vous devez être connecté en tant que membre du groupe RTCUniversalServerAdmins. Pour demander un certificat à partir d’une autorité de certification publique, il n’est pas nécessaire que vous soyez membre d’autres groupes. Pour demander un certificat auprès de l’infrastructure à clé publique (PKI) de votre organisation, vous devez confirmer les appartenances de groupe supplémentaires, le cas besoin. Au cours de la tâche Demander, vous pouvez entrer d’autres informations d’identification qui seront utilisées pour demander le certificat auprès de l’ac émettrice de votre PKI.
  
Pour demander un nouveau certificat, cliquez sur **Demander**.
  
Pour assigner un certificat qui n’a pas encore été assigné, cliquez sur **Assigner**.
  
Pour supprimer un certificat que vous avez précédemment assigné, cliquez sur **Supprimer**.
  
> [!NOTE]
> Le bouton **Supprimer** sera disponible uniquement si un certificat a été précédemment assigné. Si le bouton **Supprimer** n’est pas disponible (grisé), cela signifie qu’aucun certificat n’a été assigné.
  
Pour afficher un certificat assigné, cliquez sur **Afficher**.
  
> [!NOTE]
> Le bouton **Afficher** sera disponible uniquement si un certificat a été précédemment assigné. Si le bouton **Afficher** est grisé, cela signifie qu’aucun certificat n’a été assigné.
  
Pour actualiser l’écran d’assignation du certificat actuel, cliquez sur **Actualiser**.
  
Pour importer un certificat qui n’est pas présent dans le magasin de certificats, cliquez sur **Importer un certificat**.
  
> [!NOTE]
> L’option **Importer un certificat** est généralement utilisée pour traiter un certificat qui est reçu par le biais d’un processus autre qu’une demande de l’Assistant Certificat. Par exemple, l’administrateur de votre infrastructure à clé publique crée un certificat et vous permet d’y accéder. Utilisez **le certificat d’importation** pour importer le certificat dans le magasin de certificats de l’ordinateur et le mettre à la disposition Skype Entreprise Server à affecter.
  
Pour achever le processus de demande de certificat auprès d’une autorité de certification de votre organisation qui nécessite l’approbation de l’administrateur de l’autorité de certification, cliquez sur **Traiter une demande en attente**. La demande de certificat affichera un statut en attente, ainsi que le numéro d’identification de la demande en attente. Pour poursuivre le traitement d’un certificat dont le statut est en attente, cliquez sur **Actualiser** pour activer le bouton **Traiter une demande en attente**. Le bouton **Traiter une demande en attente** ne sera plus inaccessible (grisé). Vous pourrez ensuite essayer de récupérer la demande en attente, mais le statut de la demande restera en attente tant que le certificat n’aura pas été émis ou rejeté par l’administrateur de l’autorité de certification. Le bouton sera inaccessible si aucune demande en attente valide n’a été créée par l’Assistant Certificat.
  

