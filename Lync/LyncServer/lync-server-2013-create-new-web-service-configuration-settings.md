---
title: 'Lync Server 2013 : création des paramètres de configuration d’un service Web'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create new Web Service configuration settings
ms:assetid: f3f04d81-8a1f-427f-bd0f-fb659024e096
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182605(v=OCS.15)
ms:contentKeyID: 48185801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e91246feaad4d5375f7f7a93597f9bc754e7b613
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007113"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-new-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="930fa-102">Créer des paramètres de configuration de service Web dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="930fa-102">Create new Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="930fa-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="930fa-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="930fa-104">Vous pouvez utiliser la page **service Web** pour configurer les méthodes d’authentification permettant d’accéder aux serveurs Web et aux services Web Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="930fa-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="930fa-105">Procédez comme suit pour créer une stratégie de service Web.</span><span class="sxs-lookup"><span data-stu-id="930fa-105">Follow these steps to create a new Web Service policy.</span></span>

<div>

## <a name="to-create-new-web-service-configuration-settings"></a><span data-ttu-id="930fa-106">Pour créer des paramètres de configuration de service Web</span><span class="sxs-lookup"><span data-stu-id="930fa-106">To create new web service configuration settings</span></span>

1.  <span data-ttu-id="930fa-107">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="930fa-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="930fa-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="930fa-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="930fa-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="930fa-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="930fa-110">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service Web**.</span><span class="sxs-lookup"><span data-stu-id="930fa-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="930fa-111">Sur la page **Service Web**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="930fa-111">On the **Web Service** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="930fa-p102">Pour configurer le service Web pour un site, cliquez sur **Configuration du site**. Dans **Sélectionner un site**, cliquez sur le site auquel le service Web s’appliquera, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="930fa-p102">To configure the Web Service for a site, click **Site configuration**. In **Select a Site**, click the site to which the Web Service policy will be applied a site and click **OK**.</span></span>
    
      - <span data-ttu-id="930fa-p103">Pour configurer le service Web pour un pool, cliquez sur **Configuration du pool**. Dans **Sélectionner un service**, cliquez sur le service auquel la stratégie de service Web s’appliquera, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="930fa-p103">To configure the Web Service for a pool, click **Pool configuration**. In **Select a Service**, click the service to which the Web Service policy will be applied and click **OK**.</span></span>

5.  <span data-ttu-id="930fa-116">Dans **Nouveau paramètre de service Web**, dans **Authentification Windows intégrée**, sélectionnez **Négocier**, **Authentification Windows intégrée** ou **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="930fa-116">In **New Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="930fa-117">Sélectionnez une ou plusieurs des options suivantes en fonction des capacités des clients et de la prise en charge dans votre environnement :</span><span class="sxs-lookup"><span data-stu-id="930fa-117">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="930fa-118">**Activer l’authentification par code confidentiel** pour pouvoir authentifier les clients au moyen de codes confidentiels.</span><span class="sxs-lookup"><span data-stu-id="930fa-118">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="930fa-119">**Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.</span><span class="sxs-lookup"><span data-stu-id="930fa-119">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="930fa-120">**Activer le téléchargement de chaîne de certificats** pour que les serveurs présentés avec un certificat d’authentification téléchargent la chaîne de certificats du certificat concerné.</span><span class="sxs-lookup"><span data-stu-id="930fa-120">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="930fa-121">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="930fa-121">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

