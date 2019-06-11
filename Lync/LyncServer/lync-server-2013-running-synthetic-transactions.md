---
title: 'Lync Server 2013: exécution de transactions de synthèse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 489b8a02d829f4f12038e3f07559166c1c015b80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="8acf9-102">Exécution de transactions de synthèse dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acf9-102">Running synthetic transactions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8acf9-103">_**Dernière modification de la rubrique:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="8acf9-103">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="8acf9-104">Les transactions synthétiques sont généralement effectuées de deux manières.</span><span class="sxs-lookup"><span data-stu-id="8acf9-104">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="8acf9-105">Vous pouvez utiliser les applets de CsHealthMonitoringConfiguration pour configurer des utilisateurs de test pour chacun de leurs pools de bureaux d’enregistrement.</span><span class="sxs-lookup"><span data-stu-id="8acf9-105">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="8acf9-106">Ces utilisateurs de test sont une paire d’utilisateurs préconfigurés pour une utilisation avec des transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="8acf9-106">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="8acf9-107">(En général, il s’agit des comptes de test et non des comptes appartenant aux utilisateurs réels.) Avec les utilisateurs test configurés pour un pool, vous pouvez exécuter une transaction synthétique sur le pool sans avoir à spécifier les identités (et fournir les informations d’identification pour) pour les comptes d’utilisateurs impliqués dans le test.</span><span class="sxs-lookup"><span data-stu-id="8acf9-107">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="8acf9-108">Vous pouvez ou non exécuter une transaction synthétique en utilisant des comptes d’utilisateurs réels.</span><span class="sxs-lookup"><span data-stu-id="8acf9-108">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="8acf9-109">Par exemple, si deux utilisateurs ne peuvent pas échanger de messages instantanés, vous pouvez exécuter une transaction de synthèse à l’aide de ces deux comptes d’utilisateur (plutôt que de deux comptes de test), puis essayer de diagnostiquer et résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="8acf9-109">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="8acf9-110">Si vous décidez d’effectuer une transaction synthétique à l’aide de comptes d’utilisateurs réels, vous devez fournir les noms de connexion et les mots de passe pour chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="8acf9-110">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8acf9-111">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="8acf9-111">See Also</span></span>


[<span data-ttu-id="8acf9-112">Configuration des utilisateurs et des paramètres de configuration du nœud FileSystemWatcher dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acf9-112">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="8acf9-113">Instructions de configuration spéciales pour les transactions synthétiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8acf9-113">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

