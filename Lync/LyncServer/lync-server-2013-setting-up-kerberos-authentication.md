---
title: 'Lync Server 2013 : configuration de l’authentification Kerberos'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Kerberos authentication
ms:assetid: dd8009ef-6265-4cc0-b2c7-e474cd1f4b09
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398976(v=OCS.15)
ms:contentKeyID: 48185601
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fc4f354d985ed9e0fc85909e232e06e7c34dd593
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509651"
---
# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="308b3-102">Configuration de l’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="308b3-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="308b3-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="308b3-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="308b3-104">Lync Server 2013 prend en charge l’authentification NTLM et l’authentification Kerberos pour les services Web.</span><span class="sxs-lookup"><span data-stu-id="308b3-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="308b3-105">Office Communications Server 2007 et Office Communications Server 2007 R2 utilisaient le RTCComponentService et le RTCService par défaut comme comptes d’utilisateur pour exécuter les pools d’applications des services Web, ce qui permet d’affecter un nom de principal du service (SPN) aux comptes d’utilisateur et d’agir en tant que principal d’authentification.</span><span class="sxs-lookup"><span data-stu-id="308b3-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="308b3-106">Lync Server utilise NetworkService pour exécuter les services Web et NetworkService ne peut pas avoir de noms principaux de service.</span><span class="sxs-lookup"><span data-stu-id="308b3-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="308b3-107">Pour résoudre le problème de non-utilisation d’objets Active Directory pour conserver les SPN, le panneau de configuration Lync Server peut utiliser des objets de compte d’ordinateur à cet effet.</span><span class="sxs-lookup"><span data-stu-id="308b3-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="308b3-108">Les objets de compte d’ordinateur peuvent contenir les noms principaux de domaine et ne font pas l’objet d’une expiration de mot de passe, ce qui était un problème lors de l’utilisation de comptes d’utilisateur dans les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="308b3-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="308b3-109">Vous utilisez les applets de commande Windows PowerShell pour configurer les objets ordinateur afin de fournir l’authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="308b3-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="308b3-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="308b3-110">In This Section</span></span>

  - [<span data-ttu-id="308b3-111">Conditions préalables à l’activation de l’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="308b3-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="308b3-112">Créer un compte d’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="308b3-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="308b3-113">Affecter un compte d’authentification Kerberos à un site dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="308b3-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="308b3-114">Configuration des mots de passe de compte d’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="308b3-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="308b3-115">Dans Lync Server 2013, ajoutez l’authentification Kerberos à d’autres sites</span><span class="sxs-lookup"><span data-stu-id="308b3-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="308b3-116">Dans Lync Server 2013, supprimez l’authentification Kerberos d’un site.</span><span class="sxs-lookup"><span data-stu-id="308b3-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="308b3-117">Test et création de rapports sur l’État et l’affectation de l’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="308b3-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

