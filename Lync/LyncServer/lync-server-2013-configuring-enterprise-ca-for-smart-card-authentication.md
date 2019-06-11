---
title: 'Lync Server 2013: configuration d’une autorité de certification d’entreprise pour l’authentification par carte à puce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 890a69d1c863702db0a70cfb2ce3d61f6a75eeae
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838258"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="53eb2-102">Configuration de l’autorité de certification d’entreprise pour l’authentification par carte à puce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53eb2-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53eb2-103">_**Dernière modification de la rubrique:** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="53eb2-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="53eb2-104">La section suivante décrit comment configurer une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce.</span><span class="sxs-lookup"><span data-stu-id="53eb2-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="53eb2-105">Pour plus d’informations sur l’installation d’une autorité de certification racine d’entreprise, voir installer une [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364)autorité de certification racine d’entreprise à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="53eb2-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [http://go.microsoft.com/fwlink/p/?LinkID=313364](http://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="53eb2-106">Configuration d’une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce</span><span class="sxs-lookup"><span data-stu-id="53eb2-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="53eb2-107">La procédure ci-dessous décrit la configuration d’une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce :</span><span class="sxs-lookup"><span data-stu-id="53eb2-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="53eb2-108">Connectez-vous à l’ordinateur de l’autorité de certification d’entreprise à l’aide d’un compte d’administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="53eb2-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="53eb2-109">Lancez le gestionnaire système, puis vérifiez que le rôle Inscription de l’autorité de certification par le biais du web est installé.</span><span class="sxs-lookup"><span data-stu-id="53eb2-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="53eb2-110">Dans le menu **Outils d’administration**, ouvrez la console de gestion **Autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="53eb2-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="53eb2-111">Dans le volet de navigation, développez **Autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="53eb2-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="53eb2-112">Cliquez avec le bouton droit sur **Modèles de certificat**, sélectionnez **Nouveau**, puis **Modèle de certificat à délivrer**.</span><span class="sxs-lookup"><span data-stu-id="53eb2-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="53eb2-113">Sélectionnez **Agent d’inscription**, **Utilisateur de carte à puce** et **Connexion par carte à puce**.</span><span class="sxs-lookup"><span data-stu-id="53eb2-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="53eb2-114">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="53eb2-114">Click **OK**.</span></span>

8.  <span data-ttu-id="53eb2-115">Cliquez avec le bouton droit sur **Modèles de certificat**.</span><span class="sxs-lookup"><span data-stu-id="53eb2-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="53eb2-116">Sélectionnez **Gérer**.</span><span class="sxs-lookup"><span data-stu-id="53eb2-116">Select **Manage**.</span></span>

10. <span data-ttu-id="53eb2-117">Ouvrez les propriétés du modèle utilisateur de carte à puce.</span><span class="sxs-lookup"><span data-stu-id="53eb2-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="53eb2-118">Cliquez sur l’onglet **Sécurité**.</span><span class="sxs-lookup"><span data-stu-id="53eb2-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="53eb2-119">Modifiez les autorisations, comme suit :</span><span class="sxs-lookup"><span data-stu-id="53eb2-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="53eb2-120">Ajoutez des comptes Active Directory d’utilisateurs individuels avec les autorisations Lire/Inscrire (Autoriser) ou</span><span class="sxs-lookup"><span data-stu-id="53eb2-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="53eb2-121">Ajoutez un groupe de sécurité contenant des utilisateurs de carte à puce avec les autorisations Lire/Inscrire (Autoriser) ou</span><span class="sxs-lookup"><span data-stu-id="53eb2-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="53eb2-122">Ajoutez le groupe Utilisateurs du domaine avec les autorisations Lire/Inscrire (Autoriser).</span><span class="sxs-lookup"><span data-stu-id="53eb2-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

