---
title: Importer un certificat (introduction)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
ROBOTS: NOINDEX, NOFOLLOW
description: Pour importer un certificat, vous devez fournir un chemin d’accès au fichier du certificat. Dans la zone de texte fichier de sélectionner un certificat, vous pouvez tapez le chemin d’accès complet et le nom de fichier, ou cliquez sur le bouton Parcourir et naviguez jusqu'à l’emplacement du chemin d’accès et le nom de fichier (en règle générale, un fichier .p7b, .pfx ou .cer).
ms.openlocfilehash: 6b6c8dcdb210d2203ab5148474df76b56d3a5ad7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893937"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="0ee04-104">Importer un certificat (introduction)</span><span class="sxs-lookup"><span data-stu-id="0ee04-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="0ee04-105">Pour importer un certificat, vous devez fournir un chemin d’accès au fichier du certificat.</span><span class="sxs-lookup"><span data-stu-id="0ee04-105">To import a certificate, you must provide a path to the certificate file.</span></span> <span data-ttu-id="0ee04-106">Dans la zone de texte **fichier de sélectionner un certificat** , vous pouvez tapez le chemin d’accès complet et le nom de fichier, ou cliquez sur le bouton **Parcourir** et naviguez jusqu'à l’emplacement du chemin d’accès et le nom de fichier (en règle générale, un fichier .p7b, .pfx ou .cer).</span><span class="sxs-lookup"><span data-stu-id="0ee04-106">In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="0ee04-107">Si le certificat contient une clé privée, activez la case à cocher **fichier de certificat contient la clé privée du certificat**.</span><span class="sxs-lookup"><span data-stu-id="0ee04-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="0ee04-108">Lorsque cette case à cocher est activée, l’entrée de texte **mot de passe** est activée.</span><span class="sxs-lookup"><span data-stu-id="0ee04-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="0ee04-109">Si vous avez un certificat avec une clé privée qui lui est associée, un mot de passe est généralement placée sur la clé privée lorsque le certificat est créé.</span><span class="sxs-lookup"><span data-stu-id="0ee04-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="0ee04-110">Vous entrez le mot de passe pour la clé privée pour autoriser le certificat et la clé privée à importer dans le magasin de certificats.</span><span class="sxs-lookup"><span data-stu-id="0ee04-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="0ee04-111">Lorsque vous avez fourni les informations pour le chemin d’accès du fichier de certificat et éventuellement le mot de passe clé privée, si nécessaire, cliquez sur **suivant**.</span><span class="sxs-lookup"><span data-stu-id="0ee04-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0ee04-112">Si vous ne connaissez pas le mot de passe pour la clé privée, l’importation échouera.</span><span class="sxs-lookup"><span data-stu-id="0ee04-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

