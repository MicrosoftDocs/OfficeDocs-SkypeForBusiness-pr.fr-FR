---
title: Préparer Active Directory
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: Pour commencer l’installation de Skype pour Business Server, vous devez préparer le schéma Active Directory Domain Services, la forêt et les domaines qui hébergeront des serveurs et des utilisateurs. Le Skype pour l’Assistant de déploiement Business Server vous guidera tout au long des étapes requises pour préparer Active Directory, commence avec le schéma, puis dans la préparation de la forêt. Après avoir confirmé que la réplication Active Directory est accessible, vous préparer puis chaque domaine qui hébergera les utilisateurs ou les serveurs.
ms.openlocfilehash: 501fbfe8b98e7334386e116c76812502f92ac53c
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20987655"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="59808-105">Préparer Active Directory</span><span class="sxs-lookup"><span data-stu-id="59808-105">Prepare Active Directory</span></span>
 
<span data-ttu-id="59808-106">Pour commencer l’installation de Skype pour Business Server, vous devez préparer le schéma Active Directory Domain Services, la forêt et les domaines qui hébergeront des serveurs et des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="59808-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="59808-107">Le Skype pour l’Assistant de déploiement Business Server vous guidera tout au long des étapes requises pour préparer Active Directory, commence avec le schéma, puis dans la préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="59808-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="59808-108">Après avoir confirmé que la réplication Active Directory est accessible, vous préparer puis chaque domaine qui hébergera les utilisateurs ou les serveurs.</span><span class="sxs-lookup"><span data-stu-id="59808-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="59808-p103">Pour préparer efficacement le schéma, vous devez être connecté en tant que membre du groupe Administrateurs d’entreprise et du groupe Administrateurs du schéma. Pour préparer la forêt, vous devez être connecté en tant que membre du groupe Administrateurs d’entreprise ou être connecté en tant qu’administrateur dans la racine de la forêt. Pour la préparation du domaine, vous devez vous connecter en tant que membre du groupe Administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="59808-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span> 
  
<span data-ttu-id="59808-112">Pour plus d’informations sur les topologies Active Directory prises en charge, voir [Prise en charge de Active Directory](http://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) dans la documentation de prise en charge.</span><span class="sxs-lookup"><span data-stu-id="59808-112">For details about supported Active Directory topologies, see [Active Directory Support](http://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation.</span></span> <span data-ttu-id="59808-113">Pour plus d’informations sur la préparation d’Active Directory, voir [Vue d’ensemble du domaine Services préparation d’Active Directory](http://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="59808-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](http://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>
  

