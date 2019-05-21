---
title: Préparer Active Directory
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainADPrep
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8c96311-9e1c-4d39-9870-681fd4e272ff
ROBOTS: NOINDEX, NOFOLLOW
description: Pour commencer l’installation de Skype entreprise Server, vous devez préparer le schéma des services de domaine Active Directory, la forêt et les domaines qui hébergeront les serveurs et les utilisateurs. L’Assistant Déploiement de Skype entreprise Server vous guidera tout au long des étapes requises pour préparer Active Directory, en commençant par le schéma puis dans la préparation de la forêt. Après confirmation de la réussite de la réplication Active Directory, vous préparez chacun des domaines qui hébergeront des utilisateurs ou des serveurs.
ms.openlocfilehash: e4de6019303b53a1828d7ee271194ebca107b0c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276295"
---
# <a name="prepare-active-directory"></a><span data-ttu-id="fe4d2-105">Préparer Active Directory</span><span class="sxs-lookup"><span data-stu-id="fe4d2-105">Prepare Active Directory</span></span>

<span data-ttu-id="fe4d2-106">Pour commencer l’installation de Skype entreprise Server, vous devez préparer le schéma des services de domaine Active Directory, la forêt et les domaines qui hébergeront les serveurs et les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-106">To begin the installation of Skype for Business Server, you must prepare the Active Directory Domain Services schema, forest, and domains that will host servers and users.</span></span> <span data-ttu-id="fe4d2-107">L’Assistant Déploiement de Skype entreprise Server vous guidera tout au long des étapes requises pour préparer Active Directory, en commençant par le schéma puis dans la préparation de la forêt.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-107">The Skype for Business Server Deployment Wizard will guide you through the steps required to prepare Active Directory, beginning with the schema and then into the forest preparation.</span></span> <span data-ttu-id="fe4d2-108">Après confirmation de la réussite de la réplication Active Directory, vous préparez chacun des domaines qui hébergeront des utilisateurs ou des serveurs.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-108">After confirming that Active Directory replication is successful, you then prepare each domain that will host users or servers.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe4d2-p103">Pour préparer efficacement le schéma, vous devez être connecté en tant que membre du groupe Administrateurs d’entreprise et du groupe Administrateurs du schéma. Pour préparer la forêt, vous devez être connecté en tant que membre du groupe Administrateurs d’entreprise ou être connecté en tant qu’administrateur dans la racine de la forêt. Pour la préparation du domaine, vous devez vous connecter en tant que membre du groupe Administrateurs du domaine.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-p103">To successfully prepare the schema, you must be logged in as a member of the Enterprise Admins group and the Schema Admins group. To prepare the forest, you must be logged in as a member of the Enterprise Admins group or logged in as the administrator in the forest root. For domain preparation, you must be logged in as a member of the Domain Admins group.</span></span>

<span data-ttu-id="fe4d2-p104">Pour plus d’informations sur les topologies Active Directory prises en charge, reportez-vous à [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) dans la documentation de la prise en charge. Pour plus d’informations sur la préparation d’Active Directory, reportez-vous à [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) dans la documentation du déploiement.</span><span class="sxs-lookup"><span data-stu-id="fe4d2-p104">For details about supported Active Directory topologies, see [Active Directory Support](https://technet.microsoft.com/library/28ed9ac4-586d-4803-ad45-99c4fa793f54.aspx) in the Supportability documentation. For details about the Active Directory preparation, see [Overview of Active Directory Domain Services Preparation](https://technet.microsoft.com/library/cdd2a652-6a0d-4728-9950-3fcaa7a80066.aspx) in the Deployment documentation.</span></span>


