---
title: 'Lync Server 2013 : configuration de l’autorité de certification d’entreprise pour l’authentification par carte à puce'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise CA for smart card authentication
ms:assetid: c24e0891-e108-4cb6-9902-c6a4c8e68455
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn308571(v=OCS.15)
ms:contentKeyID: 54973692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: abfbbb7a7f7787ab5490db1542c4435368a84ca0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532561"
---
# <a name="configuring-enterprise-ca-for-smart-card-authentication-in-lync-server-2013"></a><span data-ttu-id="1e98c-102">Configuration de l’autorité de certification d’entreprise pour l’authentification par carte à puce dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e98c-102">Configuring Enterprise CA for smart card authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e98c-103">_**Dernière modification de la rubrique :** 2013-07-03_</span><span class="sxs-lookup"><span data-stu-id="1e98c-103">_**Topic Last Modified:** 2013-07-03_</span></span>

<span data-ttu-id="1e98c-104">La section suivante décrit la configuration d’une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce.</span><span class="sxs-lookup"><span data-stu-id="1e98c-104">The following section describes how to configure an Enterprise Root Certification Authority (CA) to support smart card authentication.</span></span> <span data-ttu-id="1e98c-105">Pour plus d’informations sur l’installation d’une autorité de certification racine d’entreprise, consultez la rubrique installer une autorité de certification racine d’entreprise à l’adresse [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364) .</span><span class="sxs-lookup"><span data-stu-id="1e98c-105">For information on how to install an Enterprise Root CA, see Install an Enterprise Root Certification Authority at [https://go.microsoft.com/fwlink/p/?LinkID=313364](https://go.microsoft.com/fwlink/p/?linkid=313364).</span></span>

<div>

## <a name="configuring-an-enterprise-root-certificate-authority-to-support-smart-card-authentication"></a><span data-ttu-id="1e98c-106">Configuration d’une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce</span><span class="sxs-lookup"><span data-stu-id="1e98c-106">Configuring an Enterprise Root Certificate Authority to Support Smart Card Authentication</span></span>

<span data-ttu-id="1e98c-107">Les étapes suivantes décrivent comment configurer une autorité de certification racine d’entreprise pour prendre en charge l’authentification par carte à puce :</span><span class="sxs-lookup"><span data-stu-id="1e98c-107">The following steps describe how to configure an Enterprise Root CA to support Smart Card Authentication:</span></span>

1.  <span data-ttu-id="1e98c-108">Connectez-vous à l’ordinateur de l’autorité de certification d’entreprise à l’aide d’un compte d’administrateur de domaine.</span><span class="sxs-lookup"><span data-stu-id="1e98c-108">Log in to the Enterprise CA computer using a Domain Admin account.</span></span>

2.  <span data-ttu-id="1e98c-109">Lancez le Gestionnaire système et assurez-vous que le rôle d’inscriptions par le Web de l’autorité de certification est installé.</span><span class="sxs-lookup"><span data-stu-id="1e98c-109">Launch System Manager, and verify that the Certificate Authority Web Enrollment role is installed.</span></span>

3.  <span data-ttu-id="1e98c-110">Dans le menu **Outils d’administration** , ouvrez la console de gestion **autorité de certification** .</span><span class="sxs-lookup"><span data-stu-id="1e98c-110">From the **Administrative Tools** menu, open the **Certification Authority** management console.</span></span>

4.  <span data-ttu-id="1e98c-111">Dans le volet de navigation, développez **autorité de certification**.</span><span class="sxs-lookup"><span data-stu-id="1e98c-111">In the Navigation pane, expand **Certification Authority**.</span></span>

5.  <span data-ttu-id="1e98c-112">Cliquez avec le bouton droit sur **modèles de certificats**, sélectionnez **nouveau**, puis **modèle de certificat à délivrer**.</span><span class="sxs-lookup"><span data-stu-id="1e98c-112">Right click on **Certificate Templates**, select **New**, then select **Certificate Template to Issue**.</span></span>

6.  <span data-ttu-id="1e98c-113">Sélectionnez **agent d’enregistrement**, **utilisateur de carte à puce**et ouverture de session par carte à **puce**.</span><span class="sxs-lookup"><span data-stu-id="1e98c-113">Select **Enrollment Agent**, **Smartcard User**, and **Smartcard Logon**.</span></span>

7.  <span data-ttu-id="1e98c-114">Cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="1e98c-114">Click **OK**.</span></span>

8.  <span data-ttu-id="1e98c-115">Cliquez avec le bouton droit sur **modèles de certificats**.</span><span class="sxs-lookup"><span data-stu-id="1e98c-115">Right click on **Certificate Templates**.</span></span>

9.  <span data-ttu-id="1e98c-116">Sélectionnez **gérer**.</span><span class="sxs-lookup"><span data-stu-id="1e98c-116">Select **Manage**.</span></span>

10. <span data-ttu-id="1e98c-117">Ouvrez les propriétés du modèle utilisateur SmartCard.</span><span class="sxs-lookup"><span data-stu-id="1e98c-117">Open the properties of the Smartcard User template.</span></span>

11. <span data-ttu-id="1e98c-118">Cliquez sur l’onglet **sécurité** .</span><span class="sxs-lookup"><span data-stu-id="1e98c-118">Click on the **Security** tab.</span></span>

12. <span data-ttu-id="1e98c-119">Modifiez les autorisations comme suit :</span><span class="sxs-lookup"><span data-stu-id="1e98c-119">Change the permissions as follows:</span></span>
    
      - <span data-ttu-id="1e98c-120">Ajouter des comptes AD d’utilisateur individuels avec des autorisations Lecture/inscription (autoriser) ou</span><span class="sxs-lookup"><span data-stu-id="1e98c-120">Add individual user AD accounts with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="1e98c-121">Ajouter un groupe de sécurité contenant des utilisateurs de carte à puce avec des autorisations Lecture/inscription (autoriser) ou</span><span class="sxs-lookup"><span data-stu-id="1e98c-121">Add a security group containing smart card users with Read/Enroll (Allow) permissions, or</span></span>
    
      - <span data-ttu-id="1e98c-122">Ajouter le groupe utilisateurs du domaine avec les autorisations lire/inscrire (autoriser)</span><span class="sxs-lookup"><span data-stu-id="1e98c-122">Add the Domain Users group with Read/Enroll (Allow) permissions</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

