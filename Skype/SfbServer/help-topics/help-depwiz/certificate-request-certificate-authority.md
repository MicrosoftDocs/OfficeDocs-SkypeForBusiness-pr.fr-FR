---
title: Demande de certificat (autorité de certification)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployCertRequestCA
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a609f1b0-ae13-44ca-a467-b7fb14ff18a1
description: 'Lorsque vous faites une demande de certificat auprès d’une autorité de certification en ligne (généralement à des serveurs qui se trouvent sur votre réseau interne) dans la page Choisir une autorité de certification, vous avez le choix entre deux options :'
ms.openlocfilehash: b7e3c3b230376dbb289b526d112440ce69eb574b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34302112"
---
# <a name="certificate-request-certificate-authority"></a><span data-ttu-id="ad824-103">Demande de certificat (autorité de certification)</span><span class="sxs-lookup"><span data-stu-id="ad824-103">Certificate Request (Certificate Authority)</span></span>
 
<span data-ttu-id="ad824-104">Lorsque vous faites une demande de certificat auprès d’une autorité de certification en ligne (généralement à des serveurs qui se trouvent sur votre réseau interne) dans la page **Choisir une autorité de certification**, vous avez le choix entre deux options :</span><span class="sxs-lookup"><span data-stu-id="ad824-104">When making a certificate request to an online certification authority (CA) (typically, these are servers that are on your internal network) on the **Choose a Certification Authority (CA)** page, you are presented with two options:</span></span>
  
1. <span data-ttu-id="ad824-105">Sélectionner une autorité de certification dans une liste détectée pour votre environnement.</span><span class="sxs-lookup"><span data-stu-id="ad824-105">Select a CA from the list detected in your environment.</span></span>
    
2. <span data-ttu-id="ad824-106">Indiquer une autre autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="ad824-106">Specify another certification authority.</span></span>
    
<span data-ttu-id="ad824-107">Si vous sélectionnez la première option, une liste déroulante contenant toutes les autorités de certification Windows Server détectées dans votre environnement s’affiche.</span><span class="sxs-lookup"><span data-stu-id="ad824-107">If you select the first option, you'll see a drop-down list that contains all Windows Server-based certification authorities that are detected in your environment.</span></span> <span data-ttu-id="ad824-108">Sélectionnez l’autorité de certification adaptée à votre certificat.</span><span class="sxs-lookup"><span data-stu-id="ad824-108">Select the certification authority that is appropriate for your certificate.</span></span> <span data-ttu-id="ad824-109">Il vous faudra peut-être consulter votre administrateur d’autorité de certification pour savoir quelle autorité de certification utiliser.</span><span class="sxs-lookup"><span data-stu-id="ad824-109">You may need to consult with your CA administrator to know which CA to choose.</span></span>
  
<span data-ttu-id="ad824-p102">Si vous choisissez la deuxième option, entrez le nom de domaine complet (FQDN) et l’instance d’autorité de certification pour l’autorité de certification que vous utiliserez pour votre certificat. Cette option est appropriée si l’autorité de certification que vous souhaitez utiliser n’est pas basée sur Windows Server, mais qu’elle fonctionnera pour les autorités de certification basées sur Windows Server.</span><span class="sxs-lookup"><span data-stu-id="ad824-p102">If you select the second option, type in the fully qualified domain name (FQDN) and CA instance for the certification authority that you will use for your certificate. This option is appropriate if the CA that you want to use is not a Windows Server-based CA, but will work for Windows Server-based CAs.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ad824-112">Veillez à confirmer les appartenances aux groupes qui doivent fonctionner avec la demande de certificat.</span><span class="sxs-lookup"><span data-stu-id="ad824-112">Be sure to confirm the group memberships that you need to be successful with the certificate request.</span></span> <span data-ttu-id="ad824-113">En règle générale, les autorités de certification disposent d’une condition d’autorisation différente de celle requise pour l’installation de Skype entreprise Server sur des serveurs.</span><span class="sxs-lookup"><span data-stu-id="ad824-113">Typically, certification authorities have a different permission requirement from the requirements for installing Skype for Business Server on servers.</span></span> <span data-ttu-id="ad824-114">Vérifiez les conditions requises pour effectuer la demande de certificat auprès de votre administrateur d’autorité de certification.</span><span class="sxs-lookup"><span data-stu-id="ad824-114">Confirm the requirements for requesting the certificate with your CA administrator.</span></span> 
  

