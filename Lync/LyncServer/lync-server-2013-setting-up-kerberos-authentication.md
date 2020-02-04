---
title: 'Lync Server 2013 : Configuration de l’authentification Kerberos'
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
ms.openlocfilehash: 8c644dd613b3186b314e8fc78b42197709286200
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732214"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-kerberos-authentication-in-lync-server-2013"></a><span data-ttu-id="3e1c6-102">Configuration de l’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e1c6-102">Setting up Kerberos authentication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3e1c6-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="3e1c6-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="3e1c6-104">Lync Server 2013 prend en charge l’authentification NTLM et Kerberos pour les services Web.</span><span class="sxs-lookup"><span data-stu-id="3e1c6-104">Lync Server 2013 supports NTLM and Kerberos authentication for Web Services.</span></span> <span data-ttu-id="3e1c6-105">Office Communications Server 2007 et Office Communications Server 2007 R2 utilisait le RTCComponentService et RTCService par défaut en tant que comptes d’utilisateurs pour exécuter les pools d’applications de services Web, permettant ainsi à l’utilisateur d’utiliser un nom de principal de service (SPN). comptes et agissant en tant que principal d’authentification.</span><span class="sxs-lookup"><span data-stu-id="3e1c6-105">Office Communications Server 2007 and Office Communications Server 2007 R2 used the default RTCComponentService and RTCService as the user accounts to run the Web Services application pools, allowing for a service principal name (SPN) to be assigned to the user accounts and to act as the authentication principal.</span></span> <span data-ttu-id="3e1c6-106">Lync Server utilise NetworkService pour exécuter les services Web et NetworkService ne peut pas avoir de SPN qui lui est affecté.</span><span class="sxs-lookup"><span data-stu-id="3e1c6-106">Lync Server uses NetworkService to run Web Services and NetworkService cannot have SPNs assigned to it.</span></span>

<span data-ttu-id="3e1c6-107">Pour résoudre le problème que vous n’avez pas d’objets Active Directory devant contenir les noms d’application (SPN), le panneau de configuration de Lync Server peut utiliser les objets de compte d’ordinateur.</span><span class="sxs-lookup"><span data-stu-id="3e1c6-107">To solve the issue of not having Active Directory objects to hold the SPNs, Lync Server Control Panel can use computer account objects for this purpose.</span></span> <span data-ttu-id="3e1c6-108">Les objets de compte d’ordinateur peuvent contenir les SPN et ne sont pas soumis à l’expiration du mot de passe, ce qui fut un problème lors de l’utilisation de comptes d’utilisateur dans les versions précédentes.</span><span class="sxs-lookup"><span data-stu-id="3e1c6-108">The computer account objects can hold the SPNs and are not subject to password expiration, which was an issue with using user accounts in previous versions.</span></span>

<span data-ttu-id="3e1c6-109">Les applets de cmdlet Windows PowerShell vous permettent de configurer les objets ordinateur pour fournir une authentification Kerberos.</span><span class="sxs-lookup"><span data-stu-id="3e1c6-109">You use Windows PowerShell cmdlets to configure the computer objects to provide Kerberos authentication.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3e1c6-110">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="3e1c6-110">In This Section</span></span>

  - [<span data-ttu-id="3e1c6-111">Conditions prérequises à l’activation de l’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e1c6-111">Prerequisites for enabling Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-prerequisites-for-enabling-kerberos-authentication.md)

  - [<span data-ttu-id="3e1c6-112">Création d’un compte d’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e1c6-112">Create a Kerberos authentication account in Lync Server 2013</span></span>](lync-server-2013-create-a-kerberos-authentication-account.md)

  - [<span data-ttu-id="3e1c6-113">Attribution d’un compte d’authentification Kerberos sur un site dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e1c6-113">Assign a Kerberos authentication account to a site in Lync Server 2013</span></span>](lync-server-2013-assign-a-kerberos-authentication-account-to-a-site.md)

  - [<span data-ttu-id="3e1c6-114">Configuration des mots de passe de compte d’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e1c6-114">Setting up Kerberos authentication account passwords in Lync Server 2013</span></span>](lync-server-2013-setting-up-kerberos-authentication-account-passwords.md)

  - [<span data-ttu-id="3e1c6-115">Ajout d’une authentification Kerberos à d’autres sites dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e1c6-115">In Lync Server 2013 add Kerberos authentication to other sites</span></span>](lync-server-2013-add-kerberos-authentication-to-other-sites.md)

  - [<span data-ttu-id="3e1c6-116">Suppression de l’authentification Kerberos d’un site dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e1c6-116">In Lync Server 2013 remove Kerberos authentication from a site</span></span>](lync-server-2013-remove-kerberos-authentication-from-a-site.md)

  - [<span data-ttu-id="3e1c6-117">Test et création de rapports sur l’état et l’affectation de l’authentification Kerberos dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e1c6-117">Testing and reporting the status and assignment of Kerberos authentication in Lync Server 2013</span></span>](lync-server-2013-testing-and-reporting-the-status-and-assignment-of-kerberos-authentication.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

