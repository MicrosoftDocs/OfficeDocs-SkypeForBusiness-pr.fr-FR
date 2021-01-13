---
title: Importer un certificat (introduction)
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployCertImportBasics
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 474fac52-0b11-45dd-a211-fd2f1727238b
description: Pour importer un certificat, vous devez fournir un chemin d’accès au fichier de certificat. Dans la zone de texte Sélectionner un fichier de certificat, vous pouvez au choix entrer le chemin d’accès complet et le nom de fichier ou cliquer sur le bouton Parcourir et accéder à l’emplacement du chemin d’accès et du nom de fichier (généralement un fichier .p7b, .pfx ou .cer).
ms.openlocfilehash: 2ca89291376c488426001e1ff42c4925da58a3e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827284"
---
# <a name="import-certificate-intro"></a><span data-ttu-id="f4c8c-104">Importer un certificat (introduction)</span><span class="sxs-lookup"><span data-stu-id="f4c8c-104">Import Certificate (Intro)</span></span>
 
<span data-ttu-id="f4c8c-p102">Pour importer un certificat, vous devez fournir un chemin d’accès au fichier de certificat. Dans la zone de texte **Sélectionner un fichier de certificat**, vous pouvez au choix entrer le chemin d’accès complet et le nom de fichier ou cliquer sur le bouton **Parcourir** et accéder à l’emplacement du chemin d’accès et du nom de fichier (généralement un fichier .p7b, .pfx ou .cer).</span><span class="sxs-lookup"><span data-stu-id="f4c8c-p102">To import a certificate, you must provide a path to the certificate file. In the **Select Certificate file** text box, you can either type the full path and file name, or click the **Browse** button and navigate to the path location and the file name (typically, a .p7b, .pfx, or .cer file).</span></span>
  
<span data-ttu-id="f4c8c-107">Si le certificat contient une clé privée, cochez la case Le fichier de certificat contient **la clé privée du certificat.**</span><span class="sxs-lookup"><span data-stu-id="f4c8c-107">If the certificate contains a private key, select the check box **Certificate file contains certificate's private key**.</span></span> <span data-ttu-id="f4c8c-108">Lorsque cette case à cochée est activée, la saisie de texte **Mot de passe** est activée.</span><span class="sxs-lookup"><span data-stu-id="f4c8c-108">When this check box is selected, the **Password** text input is enabled.</span></span> <span data-ttu-id="f4c8c-109">Si vous avez un certificat qui est associé à une clé privée, un mot de passe est généralement placé sur la clé privée lors de la création du certificat.</span><span class="sxs-lookup"><span data-stu-id="f4c8c-109">If you have a certificate with a private key associated with it, a password is usually placed on the private key when the certificate is created.</span></span> <span data-ttu-id="f4c8c-110">Saisissez le mot de passe de la clé privée afin d’autoriser l’importation du certificat et de la clé privée dans le magasin de certificats.</span><span class="sxs-lookup"><span data-stu-id="f4c8c-110">You input the password for the private key to allow the certificate and the private key to be imported into the certificate store.</span></span> <span data-ttu-id="f4c8c-111">Lorsque vous avez fourni les informations pour le chemin d’accès au fichier de certificat, et éventuellement le mot de passe de la clé privée, si nécessaire, cliquez sur **Suivant**.</span><span class="sxs-lookup"><span data-stu-id="f4c8c-111">When you have provided the information for the certificate file path, and optionally the private key password, if required, click **Next**.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f4c8c-112">Si vous ne connaissez pas le mot de passe de la clé privée, l’importation échouera.</span><span class="sxs-lookup"><span data-stu-id="f4c8c-112">If you do not know the password for the private key, the import will fail.</span></span> 
  

