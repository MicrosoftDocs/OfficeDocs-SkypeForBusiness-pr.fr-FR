---
title: Préparer Active Directory
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: Pour commencer l’installation de Skype Entreprise Server, vous devez préparer le schéma, la forêt et les domaines des services de domaine Active Directory qui hébergeront les serveurs et les utilisateurs. L’Assistant Déploiement de Skype Entreprise Server vous guide à travers les étapes nécessaires pour préparer Active Directory, en commençant par le schéma, puis dans la préparation de la forêt. Après avoir confirmé que la réplication Active Directory a réussi, vous préparez ensuite chaque domaine qui hébergera des utilisateurs ou des serveurs.
ms.openlocfilehash: fcc77ed8dab3a6e3e643c2022dc45623e855dfde
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097360"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="8013a-105">Préparer Active Directory</span><span class="sxs-lookup"><span data-stu-id="8013a-105">Prepare Active Directory</span></span>

<span data-ttu-id="8013a-106">Pour commencer l’installation de Skype Entreprise Server, vous devez préparer le schéma, la forêt et les domaines des services de domaine Active Directory qui hébergeront les serveurs et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="8013a-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="8013a-107">L’Assistant Déploiement de Skype Entreprise Server vous guide à travers les étapes nécessaires pour préparer Active Directory, en commençant par le schéma, puis dans la préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="8013a-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="8013a-108">Après avoir confirmé que la réplication Active Directory a réussi, vous préparez ensuite chaque domaine qui hébergera des utilisateurs ou des serveurs.</span><span class="sxs-lookup"><span data-stu-id="8013a-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8013a-p103">Pour préparer efficacement le schéma, vous devez être connecté en tant que membre du groupe Administrateurs d’entreprise et du groupe Administrateurs du schéma. Pour préparer la forêt, vous devez être connecté en tant que membre du groupe Administrateurs d’entreprise ou être connecté en tant qu'administrateur dans la racine de la forêt. Pour la préparation du domaine, vous devez vous connecter en tant que membre du groupe Administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="8013a-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="8013a-112">Pour plus d’informations sur les topologies Active Directory prises en charge, voir [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) dans la documentation de la prise en charge.</span><span class="sxs-lookup"><span data-stu-id="8013a-112">For details about supported Active Directory topologies, see [Active Directory Support](/previous-versions/office/lync-server-2013/lync-server-2013-active-directory-support) in the Supportability documentation.</span></span> <span data-ttu-id="8013a-113">Pour plus d’informations sur la préparation d’Active Directory, voir [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) dans la documentation du déploiement.</span><span class="sxs-lookup"><span data-stu-id="8013a-113">For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-active-directory-domain-services-preparation) in the Deployment documentation.</span></span>