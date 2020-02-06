---
title: Demande de certificat (élémentaire)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: La page Paramètres de nom et de sécurité fournit une zone de texte pour définir un nom convivial, une liste déroulante pour la longueur de bits de la paire de clés privée et publique et une case à cocher vous permettant de marquer la clé privée du certificat comme étant exportable.
ms.openlocfilehash: 26315f24dd14989bd2832d6f28e591a7ae38cc64
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41796765"
---
# <a name="certificate-request-basic"></a><span data-ttu-id="66451-103">Demande de certificat (élémentaire)</span><span class="sxs-lookup"><span data-stu-id="66451-103">Certificate Request (Basic)</span></span>
 
<span data-ttu-id="66451-104">La page **paramètres de nom et de sécurité** fournit une zone de texte pour définir un **nom convivial**, une liste déroulante pour la **longueur de bits** de la paire de clés privée et publique et une case à cocher vous permettant de **marquer la clé privée du certificat comme étant exportable**.</span><span class="sxs-lookup"><span data-stu-id="66451-104">The **Name and Security Settings** page provides a text box to define a **Friendly Name**, a drop-down list for the **Bit length** of the private and public key pair, and a check box that enables you to **Mark the certificate's private key as exportable**.</span></span>
  
<span data-ttu-id="66451-105">Le nom convivial sur un certificat est un nom facilement reconnaissable qui permet à la personne qui consulte le certificat de l’identifier plus facilement.</span><span class="sxs-lookup"><span data-stu-id="66451-105">The friendly, or simple, name on a certificate is an easily recognizable name that makes it easier for the person who views the certificate to identify it.</span></span>
  
<span data-ttu-id="66451-106">La longueur en bits de la paire de clés privée et publique peut être 1024, 2048 ou 4096.</span><span class="sxs-lookup"><span data-stu-id="66451-106">The Bit length of the private and public key pair can be selected as 1024, 2048, or 4096.</span></span>
  
<span data-ttu-id="66451-107">L’activation de la case à cocher **marquer la clé privée du certificat comme étant exportable** permet d’exporter et de déplacer le certificat et la clé privée vers un autre ordinateur ou serveur.</span><span class="sxs-lookup"><span data-stu-id="66451-107">Selecting the check box for **Mark the certificate's private key as exportable** allows the certificate and private key to be exported and moved to another computer or server.</span></span> <span data-ttu-id="66451-108">Le seul cas où cela est nécessaire est quand vous créez un pool de serveurs Edge pour le service d’authentification du serveur relais multimédia.</span><span class="sxs-lookup"><span data-stu-id="66451-108">The only time that this is required is when you are creating a pool of Edge Servers for the media relay authentication service (MRAS).</span></span>
  
> [!CAUTION]
> <span data-ttu-id="66451-109">Pour garantir la sécurité du certificat et de la paire de clés, vous devez sélectionner l’option marquer la clé privée du certificat comme étant exportable uniquement si elle est absolument nécessaire.</span><span class="sxs-lookup"><span data-stu-id="66451-109">To help maintain the security of the certificate and the key pair, you should select the Mark the certificate's private key as exportable option only if it is absolutely necessary.</span></span> 
  

