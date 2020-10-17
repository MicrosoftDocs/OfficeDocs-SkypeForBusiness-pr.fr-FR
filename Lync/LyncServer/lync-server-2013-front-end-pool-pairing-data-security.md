---
title: 'Lync Server 2013 : sécurité des données d’appariement de pools frontaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d86f60e81e053a1ba07878728dd9c7273bd7feeb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500721"
---
# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="590e6-102">Sécurité des données de jumelage des pools frontaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="590e6-102">Front End pool pairing data security in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="590e6-103">_**Dernière modification de la rubrique :** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="590e6-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="590e6-104">Le service de sauvegarde est un mécanisme de réplication des données introduit dans Lync Server 2013 qui transfère les données utilisateur et le contenu de conférence entre deux pools frontaux couplés en continu entre deux centres de données à des fins de récupération d’urgence.</span><span class="sxs-lookup"><span data-stu-id="590e6-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="590e6-105">Les données utilisateur contiennent les URI SIP de l’utilisateur, ainsi que les listes de contacts et les paramètres.</span><span class="sxs-lookup"><span data-stu-id="590e6-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="590e6-106">Le contenu des conférences inclut les téléchargements de Microsoft PowerPoint 2010, ainsi que les tableaux blancs utilisés dans les conférences.</span><span class="sxs-lookup"><span data-stu-id="590e6-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="590e6-107">À partir du pool source, les données utilisateur et le contenu de conférence sont exportés à partir du stockage local, zippé, transféré vers le pool cible, où il est décompressé et importé dans le stockage local.</span><span class="sxs-lookup"><span data-stu-id="590e6-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="590e6-108">Le service de sauvegarde suppose que la liaison de communication entre les deux centres de données se trouve dans le réseau d’entreprise protégé d’Internet.</span><span class="sxs-lookup"><span data-stu-id="590e6-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="590e6-109">Il ne chiffre pas les données transférées entre les deux centres de données, et n’est pas encapsulé de manière native dans un protocole sécurisé, tel que HTTPs.</span><span class="sxs-lookup"><span data-stu-id="590e6-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="590e6-110">Par conséquent, l’attaque de l’intercepteur du personnel interne au sein du réseau d’entreprise est possible.</span><span class="sxs-lookup"><span data-stu-id="590e6-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="590e6-111">Évaluation des risques de sécurité</span><span class="sxs-lookup"><span data-stu-id="590e6-111">Evaluating Security Risks</span></span>

<span data-ttu-id="590e6-112">Toute entreprise qui déploie Lync Server 2013 sur plusieurs centres de données et qui utilise la fonctionnalité de récupération d’urgence doit s’assurer que le trafic du centre de données croisée est protégé par son intranet d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="590e6-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="590e6-113">Les entreprises qui se soucient de la protection contre les attaques internes doivent sécuriser les liens de communication entre les centres de données.</span><span class="sxs-lookup"><span data-stu-id="590e6-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="590e6-114">L’hypothèse que les centres de données d’une entreprise sont protégés derrière l’intranet d’entreprise est standard.</span><span class="sxs-lookup"><span data-stu-id="590e6-114">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard.</span></span> <span data-ttu-id="590e6-115">Il existe de nombreux autres types de données sensibles d’entreprise transférées entre ces centres de données.</span><span class="sxs-lookup"><span data-stu-id="590e6-115">There are many other types of corporate sensitive data transferred among these data centers.</span></span> <span data-ttu-id="590e6-116">L’infrastructure informatique de l’entreprise est un risque catastrophique si ces liens entre les centres de données ne sont pas protégés.</span><span class="sxs-lookup"><span data-stu-id="590e6-116">The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="590e6-117">Bien que le risque d’attaques de l’intercepteur dans le réseau d’entreprise existe, il est relativement important par rapport à l’exposition du trafic sur Internet.</span><span class="sxs-lookup"><span data-stu-id="590e6-117">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet.</span></span> <span data-ttu-id="590e6-118">Plus précisément, les données utilisateur exposées par le service de sauvegarde (comme les URI SIP) sont généralement accessibles à tous les employés au sein de l’entreprise par le biais d’autres moyens tels que le carnet d’adresses global d’Exchange ou d’autres logiciels d’annuaire.</span><span class="sxs-lookup"><span data-stu-id="590e6-118">Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software.</span></span> <span data-ttu-id="590e6-119">Par conséquent, la sécurisation du réseau étendu doit être activée entre les deux centres de données lorsque le service de sauvegarde est utilisé pour copier les données entre les deux pools couplés.</span><span class="sxs-lookup"><span data-stu-id="590e6-119">Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="590e6-120">Atténuation des risques de sécurité</span><span class="sxs-lookup"><span data-stu-id="590e6-120">Mitigating Security Risks</span></span>

<span data-ttu-id="590e6-121">Il existe de nombreuses façons d’améliorer la sécurité du trafic du service de sauvegarde, qu’il s’agisse de restreindre l’accès aux centres de données pour sécuriser le transport WAN entre les deux centres de données.</span><span class="sxs-lookup"><span data-stu-id="590e6-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="590e6-122">Dans la plupart des cas, les entreprises déployant Lync Server 2013 peuvent avoir déjà l’infrastructure de sécurité requise en place.</span><span class="sxs-lookup"><span data-stu-id="590e6-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="590e6-123">Pour les entreprises qui cherchent des conseils, Microsoft propose une solution comme exemple de création d’une infrastructure informatique sécurisée.</span><span class="sxs-lookup"><span data-stu-id="590e6-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="590e6-124">Toutefois, cela ne signifie pas qu’il s’agit de la seule solution, ni qu’il s’agit de la solution par défaut pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="590e6-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="590e6-125">Nous recommandons aux clients d’entreprise de choisir la solution qui répond à leurs besoins spécifiques en fonction de leurs besoins et de l’infrastructure de sécurité informatique. L’exemple de solution Microsoft utilise IPSec et la stratégie de groupe pour l’isolation de serveur et de domaine.</span><span class="sxs-lookup"><span data-stu-id="590e6-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="590e6-126">Pour plus d’informations, reportez-vous à [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544) .</span><span class="sxs-lookup"><span data-stu-id="590e6-126">For details, see [https://go.microsoft.com/fwlink/p/?LinkId=268544](https://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="590e6-127">Pour obtenir des questions et des commentaires, contactez secwish@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="590e6-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="590e6-128">Une autre solution possible consiste à utiliser IPSec uniquement pour sécuriser les données envoyées par le service de sauvegarde lui-même.</span><span class="sxs-lookup"><span data-stu-id="590e6-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="590e6-129">Si vous choisissez cette méthode, vous devez configurer les règles IPSec pour le protocole SMB pour les serveurs suivants, où le pool A et le pool B sont deux pools frontaux couplés.</span><span class="sxs-lookup"><span data-stu-id="590e6-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="590e6-130">Service SMB (TCP/445) de chaque serveur frontal dans le pool A vers le magasin de fichiers utilisé par le pool B.</span><span class="sxs-lookup"><span data-stu-id="590e6-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="590e6-131">Service SMB (TCP/445) de chaque serveur frontal dans le pool B vers le magasin de fichiers utilisé par le pool A.</span><span class="sxs-lookup"><span data-stu-id="590e6-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="590e6-132">IPsec n’est pas destiné à remplacer la sécurité au niveau de l’application, comme SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="590e6-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="590e6-133">L’un des avantages de l’utilisation d’IPsec est qu’elle permet de sécuriser le trafic réseau pour les applications existantes sans qu’il soit nécessaire de les modifier.</span><span class="sxs-lookup"><span data-stu-id="590e6-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="590e6-134">Les entreprises qui souhaitent sécuriser le transport entre les deux centres de données doivent consulter leurs fournisseurs de matériel réseau respectifs sur les moyens de configurer des connexions WAN sécurisées à l’aide de l’équipement du fournisseur.</span><span class="sxs-lookup"><span data-stu-id="590e6-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

