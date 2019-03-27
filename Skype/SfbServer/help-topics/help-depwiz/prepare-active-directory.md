---
title: Préparer Active Directory
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/26/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Pour commencer l’installation de Skype pour Business Server 2015, vous devez préparer le schéma Active Directory Domain Services, la forêt et les domaines qui hébergeront des serveurs et des utilisateurs. Le Skype pour l’Assistant de déploiement Business Server vous guidera tout au long des étapes requises pour préparer Active Directory, commence avec le schéma, puis dans la préparation de la forêt. Après avoir confirmé que la réplication Active Directory est accessible, vous préparer puis chaque domaine qui hébergera les utilisateurs ou les serveurs.
ms.openlocfilehash: ba7cbe0b0cf571cc06637cba4e3047016e68f781
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885054"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="8b4ce-105">Préparer Active Directory</span><span class="sxs-lookup"><span data-stu-id="8b4ce-105">Prepare Active Directory</span></span>

<span data-ttu-id="8b4ce-106">Pour commencer l’installation de Skype pour Business Server 2015, vous devez préparer le schéma Active Directory Domain Services, la forêt et les domaines qui hébergeront des serveurs et des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8b4ce-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="8b4ce-107">Le Skype pour l’Assistant de déploiement Business Server vous guidera tout au long des étapes requises pour préparer Active Directory, commence avec le schéma, puis dans la préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="8b4ce-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="8b4ce-108">Après avoir confirmé que la réplication Active Directory est accessible, vous préparer puis chaque domaine qui hébergera les utilisateurs ou les serveurs.</span><span class="sxs-lookup"><span data-stu-id="8b4ce-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8b4ce-p103">Pour préparer efficacement le schéma, vous devez être connecté en tant que membre du groupe Administrateurs d’entreprise et du groupe Administrateurs du schéma. Pour préparer la forêt, vous devez être connecté en tant que membre du groupe Administrateurs d’entreprise ou être connecté en tant qu’administrateur dans la racine de la forêt. Pour la préparation du domaine, vous devez vous connecter en tant que membre du groupe Administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="8b4ce-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="8b4ce-p104">Pour plus d’informations sur les topologies Active Directory prises en charge, reportez-vous à [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) dans la documentation de la prise en charge. Pour plus d’informations sur la préparation d’Active Directory, reportez-vous à [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) dans la documentation du déploiement.</span><span class="sxs-lookup"><span data-stu-id="8b4ce-p104">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation. For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


