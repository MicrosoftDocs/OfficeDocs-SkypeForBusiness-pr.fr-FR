---
title: 'Lync Server 2013 : modifier les paramètres de configuration d’un service Web existant'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Modify existing Web Service configuration settings
ms:assetid: bd9c7aa5-d31c-4fab-b31d-8baae26b1296
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182580(v=OCS.15)
ms:contentKeyID: 48185272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8a6d29868c6f4b18bd4bb02dac651a671684ecc0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043906"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-existing-web-service-configuration-settings-in-lync-server-2013"></a><span data-ttu-id="1a508-102">Modifier les paramètres de configuration d’un service Web existant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a508-102">Modify existing Web Service configuration settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a508-103">_**Dernière modification de la rubrique :** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1a508-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1a508-104">Vous pouvez utiliser la page **service Web** pour configurer les méthodes d’authentification permettant d’accéder aux serveurs Web et aux services Web Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a508-104">You can use the **Web Service** page to configure the authentication methods for accessing Lync Server 2013 related web servers and Web Services.</span></span>

<span data-ttu-id="1a508-105">Procédez comme suit pour modifier une stratégie de service web existante.</span><span class="sxs-lookup"><span data-stu-id="1a508-105">Follow these steps to modify an existing Web Service policy.</span></span>

<div>

## <a name="to-modify-existing-web-service-configuration-settings"></a><span data-ttu-id="1a508-106">Pour modifier les paramètres de configuration d’un service Web existant</span><span class="sxs-lookup"><span data-stu-id="1a508-106">To modify existing Web service configuration settings</span></span>

1.  <span data-ttu-id="1a508-107">À partir d’un compte d’utilisateur membre du groupe RTCUniversalServerAdmins (ou disposant des mêmes droits), ou affecté au rôle CsServerAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur qui se trouve sur le réseau sur lequel vous avez déployé Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1a508-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="1a508-108">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1a508-108">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1a508-109">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1a508-109">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1a508-110">Dans la barre de navigation de gauche, cliquez sur **Sécurité**, puis sur **Service web**.</span><span class="sxs-lookup"><span data-stu-id="1a508-110">In the left navigation bar, click **Security** and then click **Web Service**.</span></span>

4.  <span data-ttu-id="1a508-111">Dans la page **Service web**, cliquez successivement sur une configuration, sur le menu **Edition**, puis sur **Afficher les détails**.</span><span class="sxs-lookup"><span data-stu-id="1a508-111">On the **Web Service** page, click a configuration, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="1a508-112">Dans **Modifier le paramètre de service web**, sous **Authentification Windows intégrée**, sélectionnez **Négocier**, **Authentification Windows intégrée** ou **Aucune**.</span><span class="sxs-lookup"><span data-stu-id="1a508-112">In **Edit Web Service Setting**, in **Integrated Windows authentication**, select **Negotiate**, **Integrated Windows authentication**, or **None**.</span></span>

6.  <span data-ttu-id="1a508-113">Sélectionnez une ou plusieurs des options suivantes en fonction des capacités des clients et de la prise en charge dans votre environnement :</span><span class="sxs-lookup"><span data-stu-id="1a508-113">Select one or more of the following depending on the capabilities of the clients and support in your environment:</span></span>
    
      - <span data-ttu-id="1a508-114">**Activer l’authentification par code confidentiel** pour pouvoir authentifier les clients au moyen de codes confidentiels.</span><span class="sxs-lookup"><span data-stu-id="1a508-114">**Enable PIN Authentication** to enable clients to be authenticated using PIN numbers.</span></span>
    
      - <span data-ttu-id="1a508-115">**Activer l’authentification par certificat** pour que les serveurs du pool émettent des certificats pour les clients.</span><span class="sxs-lookup"><span data-stu-id="1a508-115">**Enable certificate authentication** to have the servers in the pool issue certificates to clients.</span></span>
    
      - <span data-ttu-id="1a508-116">**Activer le téléchargement de chaîne de certificats** pour que les serveurs présentés avec un certificat d’authentification téléchargent la chaîne de certificats du certificat concerné.</span><span class="sxs-lookup"><span data-stu-id="1a508-116">**Enable certificate chain download** to have servers presented with an authentication certificate download the certificate chain for that certificate.</span></span>

7.  <span data-ttu-id="1a508-117">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="1a508-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1a508-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="1a508-118">See Also</span></span>


[<span data-ttu-id="1a508-119">Configuration de l’authentification dans le panneau de configuration Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a508-119">Configuring authentication in the Lync Server 2013 Control Panel</span></span>](lync-server-2013-configuring-authentication-in-the-lync-server-control-panel.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

