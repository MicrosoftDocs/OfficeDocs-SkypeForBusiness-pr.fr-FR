---
title: Demande de certificat (élémentaire)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployCertRequestBasics
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 2c6b40d5-207a-4ca9-a090-e43350f4968f
ROBOTS: NOINDEX, NOFOLLOW
description: La page Nom et paramètres de sécurité fournit une zone de texte qui permet de définir un nom convivial, une liste de listes de texte pour la longueur en bits de la paire de clés privées et publiques, ainsi qu’une case à cocher qui vous permet de marquer la clé privée du certificat comme exportable.
ms.openlocfilehash: 5ae91c6fbe1c84d0fee0486dec0ca2efd9717e10
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830414"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="4145f-103">Demande de certificat (élémentaire)</span><span class="sxs-lookup"><span data-stu-id="4145f-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="4145f-104">La page Nom et **paramètres** de sécurité fournit une zone de texte pour définir un nom **convivial,** une liste de listes listes pour la longueur de **bits** de la paire de clés privées et publiques, et une case à cocher qui vous permet de marquer la clé privée du certificat comme **exportable.**</span><span class="sxs-lookup"><span data-stu-id="4145f-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="4145f-105">Le nom convivial sur un certificat est un nom facilement reconnaissable qui permet à la personne qui consulte le certificat de l’identifier plus facilement.</span><span class="sxs-lookup"><span data-stu-id="4145f-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="4145f-106">La longueur en bits de la paire de clés privée et publique peut être 1024, 2048 ou 4096.</span><span class="sxs-lookup"><span data-stu-id="4145f-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="4145f-107">Si vous cochez la case Pour marquer la clé privée du certificat comme **exportable,** le certificat et la clé privée peuvent être exportés et déplacés vers un autre ordinateur ou serveur.</span><span class="sxs-lookup"><span data-stu-id="4145f-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="4145f-108">La seule fois que cela est nécessaire, c’est lorsque vous créez un pool de serveurs Edge pour le service d’authentification de relais multimédia (MRAS).</span><span class="sxs-lookup"><span data-stu-id="4145f-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="4145f-109">Pour maintenir la sécurité du certificat et de la paire de clés, vous devez sélectionner l’option Marquer la clé privée du certificat comme exportable uniquement si cela est absolument nécessaire.</span><span class="sxs-lookup"><span data-stu-id="4145f-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

