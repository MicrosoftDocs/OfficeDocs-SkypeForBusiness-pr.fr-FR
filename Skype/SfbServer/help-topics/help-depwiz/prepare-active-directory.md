---
title: Préparer Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
description: Pour commencer l’installation de Skype entreprise Server 2015, vous devez préparer le schéma des services de domaine Active Directory, la forêt et les domaines qui hébergeront les serveurs et les utilisateurs. L’Assistant Déploiement de Skype entreprise Server vous guidera tout au long des étapes requises pour préparer Active Directory, en commençant par le schéma puis dans la préparation de la forêt. Après confirmation de la réussite de la réplication Active Directory, vous préparez chacun des domaines qui hébergeront des utilisateurs ou des serveurs.
ms.openlocfilehash: c2343d0c74d2ae46c7c2b22eaaa893f023f68297
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812032"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="bba01-105">Préparer Active Directory</span><span class="sxs-lookup"><span data-stu-id="bba01-105">Prepare Active Directory</span></span>

<span data-ttu-id="bba01-106">Pour commencer l’installation de Skype entreprise Server 2015, vous devez préparer le schéma des services de domaine Active Directory, la forêt et les domaines qui hébergeront les serveurs et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="bba01-106">To begin the installation of Skype for Business Server 2015, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="bba01-107">L’Assistant Déploiement de Skype entreprise Server vous guidera tout au long des étapes requises pour préparer Active Directory, en commençant par le schéma puis dans la préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="bba01-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="bba01-108">Après confirmation de la réussite de la réplication Active Directory, vous préparez chacun des domaines qui hébergeront des utilisateurs ou des serveurs.</span><span class="sxs-lookup"><span data-stu-id="bba01-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bba01-p103">Pour préparer efficacement le schéma, vous devez être connecté en tant que membre du groupe Administrateurs d’entreprise et du groupe Administrateurs du schéma. Pour préparer la forêt, vous devez être connecté en tant que membre du groupe Administrateurs d’entreprise ou être connecté en tant qu’administrateur dans la racine de la forêt. Pour la préparation du domaine, vous devez vous connecter en tant que membre du groupe Administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="bba01-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="bba01-p104">Pour plus d’informations sur les topologies Active Directory prises en charge, reportez-vous à [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) dans la documentation de la prise en charge. Pour plus d’informations sur la préparation d’Active Directory, reportez-vous à [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) dans la documentation du déploiement.</span><span class="sxs-lookup"><span data-stu-id="bba01-p104">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation. For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


