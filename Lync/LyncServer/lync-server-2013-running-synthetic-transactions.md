---
title: 'Lync Server 2013 : exécution de transactions synthétiques'
description: 'Lync Server 2013 : exécution de transactions synthétiques.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b0c26024f361dac196319eaf849c1847033cc9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569350"
---
# <a name="running-synthetic-transactions-in-lync-server-2013"></a><span data-ttu-id="0a14d-103">Exécution de transactions synthétiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a14d-103">Running synthetic transactions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a14d-104">_**Dernière modification de la rubrique :** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="0a14d-104">_**Topic Last Modified:** 2014-08-18_</span></span>

<span data-ttu-id="0a14d-105">Les transactions synthétiques sont généralement menées de deux manières.</span><span class="sxs-lookup"><span data-stu-id="0a14d-105">Synthetic transactions are typically conducted in two ways.</span></span> <span data-ttu-id="0a14d-106">Vous pouvez utiliser les applets de commande CsHealthMonitoringConfiguration pour configurer des utilisateurs de test pour chacun de leurs pools de serveurs d’inscriptions.</span><span class="sxs-lookup"><span data-stu-id="0a14d-106">You can use the CsHealthMonitoringConfiguration cmdlets to set up test users for each of their Registrar pools.</span></span> <span data-ttu-id="0a14d-107">Ces utilisateurs de test sont une paire d’utilisateurs qui ont été préconfigurés pour être utilisés avec des transactions synthétiques.</span><span class="sxs-lookup"><span data-stu-id="0a14d-107">These test users are a pair of users who were preconfigured for use with synthetic transactions.</span></span> <span data-ttu-id="0a14d-108">(En général, il s’agit de comptes de test et non de comptes qui appartiennent à des utilisateurs réels.) Lorsque les utilisateurs de test sont configurés pour un pool, vous pouvez exécuter une transaction synthétique sur ce pool sans avoir à spécifier les identités des comptes d’utilisateurs impliqués dans le test (et fournir les informations d’identification).</span><span class="sxs-lookup"><span data-stu-id="0a14d-108">(Typically these are test accounts and not accounts that belong to actual users.) With test users configured for a pool, you can run a synthetic transaction against that pool without having to specify the identities of (and supply the credentials for) the user accounts involved in the test.</span></span>

<span data-ttu-id="0a14d-109">Ou, vous pouvez exécuter une transaction synthétique à l’aide de comptes d’utilisateur réels.</span><span class="sxs-lookup"><span data-stu-id="0a14d-109">Or, you can run a synthetic transaction by using actual user accounts.</span></span> <span data-ttu-id="0a14d-110">Par exemple, si deux utilisateurs ne peuvent pas échanger des messages instantanés, vous pouvez exécuter une transaction synthétique en utilisant ces deux comptes d’utilisateur (au lieu d’une paire de comptes de test), puis essayer de diagnostiquer et résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="0a14d-110">For example, if two users cannot exchange instant messages, you could run a synthetic transaction using those two user accounts (instead of a pair of test accounts), and then try to diagnose and resolve the issue.</span></span> <span data-ttu-id="0a14d-111">Si vous décidez d’effectuer une transaction synthétique à l’aide de comptes d’utilisateur réels, vous devez fournir les noms de connexion et les mots de passe de chaque utilisateur.</span><span class="sxs-lookup"><span data-stu-id="0a14d-111">If you decide to conduct a synthetic transaction using actual user accounts, you must supply the logon names and passwords for each user.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0a14d-112">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0a14d-112">See Also</span></span>


[<span data-ttu-id="0a14d-113">Configuration des utilisateurs test de nœud observateur et des paramètres de configuration dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a14d-113">Configuring watcher node test users and configuration settings in Lync Server 2013</span></span>](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[<span data-ttu-id="0a14d-114">Instructions de configuration spéciales pour les transactions synthétiques dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a14d-114">Special setup instructions for synthetic transactions in Lync Server 2013</span></span>](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

