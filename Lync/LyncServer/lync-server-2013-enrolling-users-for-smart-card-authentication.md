---
title: 'Lync Server 2013 : inscription des utilisateurs pour l’authentification par carte à puce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enrolling users for smart card authentication
ms:assetid: a6445a83-a94b-423f-ba2a-12b5f84c5d75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308570(v=OCS.15)
ms:contentKeyID: 54973691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 750e77b342b48d2c81bf05e160779ca5566f5a2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="cd7bf-102">Inscription des utilisateurs à l’authentification par carte à puce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd7bf-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd7bf-103">_**Dernière modification de la rubrique :** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="cd7bf-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="cd7bf-p101">Deux méthodes permettent d’inscrire les utilisateurs pour l’authentification par carte à puce. La méthode la plus simple consiste à faire s’inscrire directement les utilisateurs pour l’authentification par carte à puce par l’inscription par le biais du web. La méthode la plus complexe implique d’utiliser un agent d’inscription. Cette rubrique décrit l’inscription automatique pour les certificats de carte à puce.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-p101">There are generally two methods for enrolling users for smart card authentication. The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent. This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="cd7bf-107">Pour plus d’informations sur l’inscription au nom des utilisateurs en tant qu’agent d’inscription, voir inscrire des certificats pour le compte d’autres utilisateurs [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367)à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [http://go.microsoft.com/fwlink/p/?LinkID=313367](http://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="cd7bf-108">Inscription des utilisateurs pour l’authentification par carte à puce</span><span class="sxs-lookup"><span data-stu-id="cd7bf-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="cd7bf-109">Connectez-vous à Windows 8 Workstation en utilisant les informations d’identification d’un utilisateur compatible Lync.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="cd7bf-110">Lancez Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="cd7bf-111">Accédez à la page d’inscription sur le Web de l' **autorité** de https://MyCA.contoso.com/certsrv)certification (par exemple,.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd7bf-112">Si vous utilisez Internet Explorer 10, vous devrez peut-être afficher ce site web en mode de compatibilité.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="cd7bf-113">Dans la page **Bienvenue**, sélectionnez **Demander un certificat**.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="cd7bf-114">Sélectionnez ensuite **Demande avancée**.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="cd7bf-115">Sélectionnez **Créer et envoyer une demande de requête auprès de cette autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="cd7bf-116">Sélectionnez **Utilisateur de carte à puce** sous la section **Modèle de certificat**, puis remplissez la demande de certificat avancée avec les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="cd7bf-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="cd7bf-117">Sous **Options des clés**, vérifiez que les paramètres suivants sont sélectionnés :</span><span class="sxs-lookup"><span data-stu-id="cd7bf-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="cd7bf-118">Sélectionnez la case d’option **Créer un jeu de clés**.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="cd7bf-119">Dans **Fournisseur de services de chiffrement**, sélectionnez **Fournisseur de services de chiffrement Microsoft pour carte à puce**.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="cd7bf-120">Dans **Utilisation de la clé**, sélectionnez **Exchange** (seule option disponible).</span><span class="sxs-lookup"><span data-stu-id="cd7bf-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="cd7bf-121">Dans **Taille de la clé**, entrez **2048**.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="cd7bf-122">Vérifiez que l’option **Nom de conteneur de clé automatique** est sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="cd7bf-123">Laissez les autres cases à cocher désactivées.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="cd7bf-124">Sous **Options supplémentaires**, vérifiez que les valeurs suivantes sont sélectionnées :</span><span class="sxs-lookup"><span data-stu-id="cd7bf-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="cd7bf-125">Dans **Format de la demande**, sélectionnez **CMC**.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="cd7bf-126">Dans **Algorithme de hachage**, sélectionnez **sha1**.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="cd7bf-127">Dans **Nom convivial**, entrez **Smardcard Certificate**.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="cd7bf-128">Si vous utilisez un lecteur de cartes à puces physiques, insérez la carte à puce dans l’appareil.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="cd7bf-129">Cliquez sur **Envoyer** pour envoyer la demande de certificat.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="cd7bf-130">Lorsque vous y êtes invité, entrez le code confidentiel utilisé pour créer la carte à puce virtuelle.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd7bf-131">La valeur par défaut du code confidentiel de la carte à puce virtuelle est « 12345678 ».</span><span class="sxs-lookup"><span data-stu-id="cd7bf-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="cd7bf-132">Une fois le certificat émis, cliquez sur **Installer ce certificat** pour terminer la procédure d’inscription.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="cd7bf-133">Si votre demande de certificat échoue avec l’erreur « Ce navigateur web ne prend pas en charge la génération des demandes de certificat », vous pouvez résoudre le problème de trois façons :</span><span class="sxs-lookup"><span data-stu-id="cd7bf-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="cd7bf-134">Activez l’affichage de compatibilité dans Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="cd7bf-135">Activez l’option Activer les paramètres Intranet dans Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="cd7bf-136">Sélectionnez le paramètre Rétablir toutes les zones au niveau par défaut sous l’onglet Sécurité du menu Options Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="cd7bf-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

