---
title: 'Lync Server 2013 : inscriptions des utilisateurs pour l’authentification par carte à puce'
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
ms.openlocfilehash: 635565936712fe542c807ea4d4c65f584e836bdc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137423"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enrolling-users-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="e904f-102">Inscrire des utilisateurs pour l’authentification par carte à puce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e904f-102">Enrolling users for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e904f-103">_**Dernière modification de la rubrique :** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="e904f-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="e904f-104">Il existe généralement deux méthodes pour inscrire des utilisateurs pour l’authentification par carte à puce.</span><span class="sxs-lookup"><span data-stu-id="e904f-104">There are generally two methods for enrolling users for smart card authentication.</span></span> <span data-ttu-id="e904f-105">La méthode la plus simple consiste à faire en sorte que les utilisateurs s’inscrivent directement pour l’authentification par carte à puce à l’aide de l’inscription Web, tandis que la méthode plus complexe implique l’utilisation d’un agent d’inscription.</span><span class="sxs-lookup"><span data-stu-id="e904f-105">The easier method involves having users enroll directly for smart card authentication using web enrollment, while the more complex method involves using an enrollment agent.</span></span> <span data-ttu-id="e904f-106">Cette rubrique se concentre sur l’auto-évaluation des certificats de carte à puce.</span><span class="sxs-lookup"><span data-stu-id="e904f-106">This topic focuses on self-enrollment for smartcard certificates.</span></span>

<span data-ttu-id="e904f-107">Pour plus d’informations sur l’inscription pour le compte des utilisateurs en tant qu’agent d’inscription, voir inscrire des certificats pour le compte d’autres [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367)utilisateurs chez.</span><span class="sxs-lookup"><span data-stu-id="e904f-107">For more information on enrolling on behalf of users as an enrollment agent, see Enroll for Certificates on Behalf of Other Users at [https://go.microsoft.com/fwlink/p/?LinkID=313367](https://go.microsoft.com/fwlink/p/?linkid=313367).</span></span>

<div>

## <a name="to-enroll-users-for-smart-card-authentication"></a><span data-ttu-id="e904f-108">Pour inscrire les utilisateurs pour l’authentification par carte à puce</span><span class="sxs-lookup"><span data-stu-id="e904f-108">To Enroll Users for Smart Card Authentication</span></span>

1.  <span data-ttu-id="e904f-109">Connectez-vous à la station de travail Windows 8 à l’aide des informations d’identification d’un utilisateur à extension Lync.</span><span class="sxs-lookup"><span data-stu-id="e904f-109">Log in to the Windows 8 workstation using the credentials of a Lync-enabled user.</span></span>

2.  <span data-ttu-id="e904f-110">Lancez Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e904f-110">Launch Internet Explorer.</span></span>

3.  <span data-ttu-id="e904f-111">Accédez à la page d' **inscriptions Web** de l’autorité de certification ( https://MyCA.contoso.com/certsrv)par exemple,.</span><span class="sxs-lookup"><span data-stu-id="e904f-111">Browse to the **Certificate Authority Web Enrollment** page (e.g. https://MyCA.contoso.com/certsrv).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e904f-112">Si vous utilisez Internet Explorer 10, vous devrez peut-être afficher ce site Web en mode de compatibilité.</span><span class="sxs-lookup"><span data-stu-id="e904f-112">If you are using Internet Explorer 10, you may need to view this website in Compatibility Mode.</span></span>

    
    </div>

4.  <span data-ttu-id="e904f-113">Sur la page d' **Accueil** , sélectionnez **demander un certificat**.</span><span class="sxs-lookup"><span data-stu-id="e904f-113">On the **Welcome** Page, select **Request a certificate**.</span></span>

5.  <span data-ttu-id="e904f-114">Ensuite, sélectionnez **demande avancée**.</span><span class="sxs-lookup"><span data-stu-id="e904f-114">Next, select **Advanced Request**.</span></span>

6.  <span data-ttu-id="e904f-115">Sélectionnez **créer et envoyer une demande à cette autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="e904f-115">Select **Create and submit a request to this CA**.</span></span>

7.  <span data-ttu-id="e904f-116">Sélectionnez **utilisateur de carte à puce** dans la section **modèle de certificat** et complétez la demande de certificat avancée avec les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e904f-116">Select **Smartcard User** under the **Certificate Template** section and complete the advanced certificate request with the following values:</span></span>
    
      - <span data-ttu-id="e904f-117">Les **options de clé** confirment les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="e904f-117">**Key Options** confirm he following settings:</span></span>
        
          - <span data-ttu-id="e904f-118">Sélectionnez la case d’option **créer un nouveau jeu de clés**</span><span class="sxs-lookup"><span data-stu-id="e904f-118">Select the **Create new key set** radio button</span></span>
        
          - <span data-ttu-id="e904f-119">Pour **CSP**, sélectionnez **Microsoft Base Smart Card crypto Provider**</span><span class="sxs-lookup"><span data-stu-id="e904f-119">For **CSP**, select **Microsoft Base Smart Card Crypto Provider**</span></span>
        
          - <span data-ttu-id="e904f-120">Pour **l’utilisation**de la clé, sélectionnez **Exchange** (il s’agit de la seule option disponible).</span><span class="sxs-lookup"><span data-stu-id="e904f-120">For **Key Usage**, select **Exchange** (this is the only option available).</span></span>
        
          - <span data-ttu-id="e904f-121">Pour **taille**de la clé, entrez **2048**</span><span class="sxs-lookup"><span data-stu-id="e904f-121">For **Key Size**, enter **2048**</span></span>
        
          - <span data-ttu-id="e904f-122">Vérifier que le **nom du conteneur de clés automatique** est sélectionné</span><span class="sxs-lookup"><span data-stu-id="e904f-122">Confirm that **Automatic key container name** is selected</span></span>
        
          - <span data-ttu-id="e904f-123">Laissez les autres cases à cocher désactivées.</span><span class="sxs-lookup"><span data-stu-id="e904f-123">Leave the other boxes unchecked.</span></span>
    
      - <span data-ttu-id="e904f-124">Sous **options supplémentaires** , confirmez les valeurs suivantes :</span><span class="sxs-lookup"><span data-stu-id="e904f-124">Under **Additional Options** confirm the following values:</span></span>
        
          - <span data-ttu-id="e904f-125">Pour **format de demande** , sélectionnez **CMC**.</span><span class="sxs-lookup"><span data-stu-id="e904f-125">For **Request Format** select **CMC**.</span></span>
        
          - <span data-ttu-id="e904f-126">Pour **algorithme de hachage** , sélectionnez **SHA1**.</span><span class="sxs-lookup"><span data-stu-id="e904f-126">For **Hash Algorithm** select **sha1**.</span></span>
        
          - <span data-ttu-id="e904f-127">Pour **nom convivial** , entrez **certificat Smardcard**.</span><span class="sxs-lookup"><span data-stu-id="e904f-127">For **Friendly Name** enter **Smardcard Certificate**.</span></span>

8.  <span data-ttu-id="e904f-128">Si vous utilisez un lecteur SmartCard physique, insérez la carte à puce dans l’appareil.</span><span class="sxs-lookup"><span data-stu-id="e904f-128">If you are using a physical smartcard reader, insert the smart card into the device.</span></span>

9.  <span data-ttu-id="e904f-129">Cliquez sur **Envoyer** pour envoyer la demande de certificat.</span><span class="sxs-lookup"><span data-stu-id="e904f-129">Click **Submit** to submit the certificate request.</span></span>

10. <span data-ttu-id="e904f-130">Lorsque vous y êtes invité, entrez le code confidentiel utilisé pour créer la carte à puce virtuelle.</span><span class="sxs-lookup"><span data-stu-id="e904f-130">When prompted, enter the PIN that was used to create the virtual smart card.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e904f-131">La valeur de code confidentiel de la carte à puce virtuelle par défaut est « 12345678 ».</span><span class="sxs-lookup"><span data-stu-id="e904f-131">The default virtual smart card PIN value is ‘12345678’.</span></span>

    
    </div>

11. <span data-ttu-id="e904f-132">Une fois le certificat émis, cliquez sur **installer ce certificat** pour terminer le processus d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="e904f-132">Once the certificate has been issued, click **Install this certificate** to complete the enrollment process.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e904f-133">Si votre demande de certificat échoue avec l’erreur « ce navigateur Web ne prend pas en charge la génération de demandes de certificats », il existe trois façons de résoudre le problème :</span><span class="sxs-lookup"><span data-stu-id="e904f-133">If your certificate request fails with the error “This Web browser does not support the generation of certificate requests,” there are three possible ways to resolve the issue:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="e904f-134">Activer l’affichage de compatibilité dans Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="e904f-134">Enable Compatibility View in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e904f-135">Activer l’option Activer les paramètres intranet dans Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="e904f-135">Enable the Turn on Intranet settings option in Internet Explorer</span></span></P>
    > <LI>
    > <P><span data-ttu-id="e904f-136">Activez le paramètre rétablir toutes les zones au niveau par défaut sous l’onglet sécurité dans le menu options d’Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="e904f-136">Select the Reset all zones to default level setting under the Security tab in the Internet Explorer options menu.</span></span></P></LI></OL>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

