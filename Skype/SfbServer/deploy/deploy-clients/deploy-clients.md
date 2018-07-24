---
title: Déploiement de clients pour Skype pour Business Server
ms.author: chucked
author: chuckedmonson
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d10abf2-d484-4fa0-8f10-4a5f9dfba4f5
description: 'Résumé : Vue d’ensemble des méthodes d’installation de client entreprise pour Skype pour les entreprises.'
ms.openlocfilehash: 31eb109f80379487ba50342817759f8d9b30acda
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985686"
---
# <a name="deploy-clients-for-skype-for-business-server"></a><span data-ttu-id="1e4cc-103">Déploiement de clients pour Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="1e4cc-103">Deploy clients for Skype for Business Server</span></span>
 
<span data-ttu-id="1e4cc-104">**Résumé :** Vue d’ensemble des méthodes d’installation de client entreprise pour Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="1e4cc-104">**Summary:** Overview of enterprise client installation methods for Skype for Business.</span></span>
  
<span data-ttu-id="1e4cc-105">Comment déployer Skype pour les entreprises à vos utilisateurs dépend de si vous avez acheté Skype pour les entreprises dans le cadre d’un plan Office 365 ou que vous avez acheté une version sous licence en volume de Skype pour les entreprises.</span><span class="sxs-lookup"><span data-stu-id="1e4cc-105">How you deploy Skype for Business to your users depends on whether you purchased Skype for Business as part of an Office 365 plan or you purchased a volume licensed version of Skype for Business.</span></span> 
  
- <span data-ttu-id="1e4cc-106">**Office 365** Si vous disposez d’un plan Office 365 qui inclut Skype pour les entreprises, la technologie d’installation qui est utilisée est appelée Click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="1e4cc-106">**Office 365** If you have an Office 365 plan that includes Skype for Business, the installation technology that's used is called Click-to-Run.</span></span> <span data-ttu-id="1e4cc-107">Avec Office 365, vous pouvez permettre à vos utilisateurs installer Skype pour les entreprises pour eux-mêmes à partir du portail Office 365.</span><span class="sxs-lookup"><span data-stu-id="1e4cc-107">With Office 365, you can let your users install Skype for Business for themselves from the Office 365 portal.</span></span> <span data-ttu-id="1e4cc-108">Ou bien, vous pouvez déployer Skype pour les entreprises à vos utilisateurs à télécharger le logiciel sur votre réseau local, puis en utilisant vos outils de déploiement de logiciels existante, comme avec Microsoft System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="1e4cc-108">Or, you can deploy Skype for Business to your users by downloading the software to your local network and then using your existing software deployment tools, such as with Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="1e4cc-109">Pour plus d’informations d’installation sur Skype pour les entreprises qui est fourni avec Office 365, voir [déployer le Skype pour client d’entreprise dans Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span><span class="sxs-lookup"><span data-stu-id="1e4cc-109">For installation information about Skype for Business that comes with Office 365, see [Deploy the Skype for Business client in Office 365](https://support.office.com/article/8c563b81-22c9-4024-9efe-9fe28c7bbc96).</span></span>
    
- <span data-ttu-id="1e4cc-110">**Avec licence en volume** Si vous disposez d’une version sous licence en volume de la Skype pour Business 2015 ou client 2016, la technologie d’installation qui est utilisée est Windows Installer (MSI).</span><span class="sxs-lookup"><span data-stu-id="1e4cc-110">**Volume licensed** If you have a volume licensed version of the Skype for Business 2015 or 2016 client, the installation technology that's used is Windows Installer (MSI).</span></span> <span data-ttu-id="1e4cc-111">Un package d’installation Windows Installer se compose de plusieurs fichiers .msi.</span><span class="sxs-lookup"><span data-stu-id="1e4cc-111">A Windows Installer-based installation package consists of multiple MSI files.</span></span> <span data-ttu-id="1e4cc-112">Pour qu’un package MSI principal indépendant de la langue soit complet, il est accompagné d’un ou de plusieurs packages spécifiques à la langue.</span><span class="sxs-lookup"><span data-stu-id="1e4cc-112">A language-neutral core MSI package is combined with one or more language-specific packages to make a complete product.</span></span> <span data-ttu-id="1e4cc-113">Le programme d’installation assemble les packages individuels et effectue des tâches de personnalisation et de maintenance pendant et après l’installation d’Office sur les ordinateurs des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="1e4cc-113">Setup assembles the individual packages and performs customization and maintenance tasks during and after installation of Office on users' computers.</span></span> <span data-ttu-id="1e4cc-114">Le Skype pour 2019 Business client utilise des programmes d’installation Click-to-Run.</span><span class="sxs-lookup"><span data-stu-id="1e4cc-114">The Skype for Business 2019 client uses Click-to-Run installers.</span></span>
    
<span data-ttu-id="1e4cc-115">Les rubriques de cette section décrivent comment utiliser et personnaliser le programme d’installation Windows pour déployer le Skype pour client d’entreprise à vos utilisateurs par le biais de vos procédures normales.</span><span class="sxs-lookup"><span data-stu-id="1e4cc-115">The topics in this section describe how to use and customize the Windows Installer to deploy the Skype for Business client to your users through your normal procedures.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e4cc-116">Le complément de réunion Skype pour Microsoft Office, qui prend en charge la gestion des réunions dans le client de messagerie et de collaboration Outlook, installe automatiquement avec Skype pour les clients d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="1e4cc-116">The Skype Meeting Add-in for Microsoft Office, which supports meeting management from within the Outlook messaging and collaboration client, installs automatically with Skype for Business clients.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="1e4cc-117">Le programme d’installation d’Office 365 ne désinstalle pas les versions précédentes de Lync.</span><span class="sxs-lookup"><span data-stu-id="1e4cc-117">The Office 365 setup program does not uninstall previous versions of Lync.</span></span> <span data-ttu-id="1e4cc-118">Le Skype pour Business client installe côte à côte avec d’autres clients Lync.</span><span class="sxs-lookup"><span data-stu-id="1e4cc-118">The Skype for Business client installs side-by-side with other Lync clients.</span></span> 
  
## <a name="installing-windows-clients"></a><span data-ttu-id="1e4cc-119">Installation des clients Windows</span><span class="sxs-lookup"><span data-stu-id="1e4cc-119">Installing Windows clients</span></span>

- [<span data-ttu-id="1e4cc-120">Personnaliser l’installation du client Windows dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="1e4cc-120">Customize Windows client installation in Skype for Business Server</span></span>](customize-windows-client-installation.md)
    
- [<span data-ttu-id="1e4cc-121">Configuration de l’expérience client avec Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="1e4cc-121">Configure the client experience with Skype for Business</span></span>](configure-the-client-experience.md)
    
- [<span data-ttu-id="1e4cc-122">Configuration de la liste de contacts dynamiques dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1e4cc-122">Configure Smart contacts list in Skype for Business Server</span></span>](configure-smart-contacts-list.md)
    
## <a name="installing-device-clients"></a><span data-ttu-id="1e4cc-123">Installation de périphériques clients</span><span class="sxs-lookup"><span data-stu-id="1e4cc-123">Installing device clients</span></span>

- [<span data-ttu-id="1e4cc-124">Skype Entreprise Server 2015 : installation et test de Skype Entreprise pour Windows Phone</span><span class="sxs-lookup"><span data-stu-id="1e4cc-124">Install and test Skype for Business for Windows Phone</span></span>](windows-phone.md)
    
- [<span data-ttu-id="1e4cc-125">Installation et test de Skype Entreprise pour iOS</span><span class="sxs-lookup"><span data-stu-id="1e4cc-125">Install and test Skype for Business for iOS</span></span>](ios.md)
    
- [<span data-ttu-id="1e4cc-126">Déploiement de Skype Room System dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1e4cc-126">Deploy Skype Room System in Skype for Business Server</span></span>](deploy-skype-room-system.md)
    
- [<span data-ttu-id="1e4cc-127">Déploiement de Skype Room System v2</span><span class="sxs-lookup"><span data-stu-id="1e4cc-127">Deploy Skype Room Systems v2</span></span>](room-systems-v2.md)
    
- [<span data-ttu-id="1e4cc-128">Déployer le Lync VDI plug-in avec Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="1e4cc-128">Deploy the Lync VDI plug-in with Skype for Business Server</span></span>](deploy-the-lync-vdi-plug-in.md)
    
- [<span data-ttu-id="1e4cc-129">Déployer des clients Web téléchargeables Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="1e4cc-129">Deploy Web downloadable clients in Skype for Business Server</span></span>](deploy-web-downloadable-clients.md)
    
- [<span data-ttu-id="1e4cc-130">Personnaliser l'expérience de client Mac dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="1e4cc-130">Customize the Mac client experience in Skype for Business</span></span>](customize-the-mac-client-experience.md)
    
## <a name="see-also"></a><span data-ttu-id="1e4cc-131">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1e4cc-131">See also</span></span>

[<span data-ttu-id="1e4cc-132">Déployer le Skype pour client d’entreprise dans Office 365</span><span class="sxs-lookup"><span data-stu-id="1e4cc-132">Deploy the Skype for Business client in Office 365</span></span>](../../../SfbOnline/set-up-skype-for-business-online/deploy-the-skype-for-business-client-in-office-365.md)