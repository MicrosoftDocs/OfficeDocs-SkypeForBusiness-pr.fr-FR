---
title: 'Lync Server 2013 : sécurité des données d’appariement de pools frontaux'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Front End pool pairing data security
ms:assetid: edb852b8-ea86-4948-b756-60fe6ee876d2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721930(v=OCS.15)
ms:contentKeyID: 49733865
ms.date: 10/07/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: db1a408aecedc14162271d5def1adc2bcebdfd82
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="front-end-pool-pairing-data-security-in-lync-server-2013"></a><span data-ttu-id="72197-102">Sécurité des données d’appariement de pools frontaux dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72197-102">Front End pool pairing data security in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72197-103">_**Dernière modification de la rubrique:** 2014-10-07_</span><span class="sxs-lookup"><span data-stu-id="72197-103">_**Topic Last Modified:** 2014-10-07_</span></span>

<span data-ttu-id="72197-104">Le service de sauvegarde est un mécanisme de réplication des données introduit dans Lync Server 2013, qui permet de transférer les données utilisateur et le contenu de la conférence entre deux listes frontales couplées en continu sur deux centres de données à des fins de reprise après sinistre.</span><span class="sxs-lookup"><span data-stu-id="72197-104">The Backup Service is a data replication mechanism introduced in Lync Server 2013 that transfers user data and conference content between two paired Front End pools continuously across two data centers for disaster recovery purposes.</span></span> <span data-ttu-id="72197-105">Les données utilisateur contiennent les URI SIP de l’utilisateur ainsi que les listes de contacts et les paramètres.</span><span class="sxs-lookup"><span data-stu-id="72197-105">The user data contains user SIP URIs as well as contact lists and settings.</span></span> <span data-ttu-id="72197-106">Le contenu de la Conférence inclut les téléchargements Microsoft PowerPoint 2010 ainsi que les tableaux blancs utilisés en conférences.</span><span class="sxs-lookup"><span data-stu-id="72197-106">Conference content includes Microsoft PowerPoint 2010 uploads, as well as whiteboards used in conferences.</span></span> <span data-ttu-id="72197-107">À partir de la liste source, les données utilisateur et le contenu de la Conférence sont exportés à partir du stockage local, compressé et transférés vers le pool cible, où il est décompressé et importé dans le stockage local.</span><span class="sxs-lookup"><span data-stu-id="72197-107">From the source pool, user data and conference content are exported from the local storage, zipped, transferred to the target Pool, where it is unzipped and imported to local storage.</span></span> <span data-ttu-id="72197-108">Le service de sauvegarde part du principe que le lien de communication entre les deux centres de données est à l’intérieur du réseau d’entreprise qui est protégé d’Internet.</span><span class="sxs-lookup"><span data-stu-id="72197-108">The Backup Service assumes that the communications link between the two data centers is within the corporate network that is protected from the Internet.</span></span> <span data-ttu-id="72197-109">Le chiffrement des données transférées entre les deux centres de données n’est pas crypté en natif au sein d’un protocole sécurisé tel que HTTPs.</span><span class="sxs-lookup"><span data-stu-id="72197-109">It does not encrypt the transferred data between the two data centers, nor is it natively encapsulated within a secure protocol, such as HTTPS.</span></span> <span data-ttu-id="72197-110">Par conséquent, il est possible d’attaquer par le biais d’une attaque par le biais du milieu interne au sein du réseau d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="72197-110">Therefore, man-in-the-middle attack from internal personnel within the corporate network is possible.</span></span>

<div>

## <a name="evaluating-security-risks"></a><span data-ttu-id="72197-111">Évaluation des risques en matière de sécurité</span><span class="sxs-lookup"><span data-stu-id="72197-111">Evaluating Security Risks</span></span>

<span data-ttu-id="72197-112">Toute entreprise qui déploie Lync Server 2013 sur plusieurs centres de données et utilise la fonctionnalité de reprise après sinistre doit garantir que le trafic du centre de données est protégé par l’intranet de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="72197-112">Any enterprise which deploys Lync Server 2013 across multiple data centers and uses the disaster recovery feature must ensure that cross-data center traffic is protected by their corporate Intranet.</span></span> <span data-ttu-id="72197-113">Les entreprises qui se soucient de la protection interne contre les attaques doivent sécuriser les liens entre les centres de données.</span><span class="sxs-lookup"><span data-stu-id="72197-113">Enterprises which care about internal attack protection must secure the communication links among the data centers.</span></span>

<span data-ttu-id="72197-114">L’hypothèse selon laquelle les centres de données d’une entreprise sont protégés au-delà de l’intranet de l’entreprise est standard.</span><span class="sxs-lookup"><span data-stu-id="72197-114">The assumption that data centers of an enterprise are protected behind the corporate Intranet is standard.</span></span> <span data-ttu-id="72197-115">Il existe de nombreux autres types de données sensibles d’entreprise transférées entre ces centres de données.</span><span class="sxs-lookup"><span data-stu-id="72197-115">There are many other types of corporate sensitive data transferred among these data centers.</span></span> <span data-ttu-id="72197-116">L’infrastructure informatique de l’entreprise est un risque catastrophique si ces liens entre les centres de données ne sont pas protégés.</span><span class="sxs-lookup"><span data-stu-id="72197-116">The enterprise’s IT infrastructure is at dire risk if these cross-data center links are not protected.</span></span>

<span data-ttu-id="72197-117">Si le risque d’attaques de l’intercepteur (« man-in-the-middle ») sur le réseau d’entreprise existe, il est relativement contrôlé en comparaison de l’exposition du trafic sur Internet.</span><span class="sxs-lookup"><span data-stu-id="72197-117">While the risk of man-in-the-middle attacks within the corporate network exists, it is relatively contained as compared to exposing the traffic to the Internet.</span></span> <span data-ttu-id="72197-118">Plus précisément, les données utilisateur exposées par le service de sauvegarde (par exemple, les URI SIP) sont généralement disponibles pour tous les employés au sein de l’entreprise via d’autres moyens tels que le carnet d’adresses global d’Exchange ou d’autres logiciels d’annuaire.</span><span class="sxs-lookup"><span data-stu-id="72197-118">Specifically, the user data exposed by Backup Service (such as SIP URIs) are generally available to all employees within the company via other means such as the Global Address Book by Exchange or other directory software.</span></span> <span data-ttu-id="72197-119">Par conséquent, le focus doit être placé sur la sécurité du réseau étendu (WAN) entre les deux centres de données lorsque le service de sauvegarde est utilisé pour copier des données entre les deux pools couplés.</span><span class="sxs-lookup"><span data-stu-id="72197-119">Hence, the focus should be on securing the WAN between the two data centers when the Backup Service is used to copy data between the two paired Pools.</span></span>

</div>

<div>

## <a name="mitigating-security-risks"></a><span data-ttu-id="72197-120">Réduction des risques liés à la sécurité</span><span class="sxs-lookup"><span data-stu-id="72197-120">Mitigating Security Risks</span></span>

<span data-ttu-id="72197-121">Il existe de nombreuses façons d’améliorer la protection de la sécurité du trafic du service de sauvegarde, qu’il s’agisse de limiter l’accès aux centres de données pour sécuriser le transport WAN entre les deux centres de données.</span><span class="sxs-lookup"><span data-stu-id="72197-121">There are many ways to enhance security protection for the Backup Service traffic, ranging from restricting access to the data centers to securing the WAN transport between the two data centers.</span></span> <span data-ttu-id="72197-122">Dans la plupart des cas, les entreprises qui déploient Lync Server 2013 peuvent avoir déjà l’infrastructure de sécurité requise en vigueur.</span><span class="sxs-lookup"><span data-stu-id="72197-122">In most cases, enterprises deploying Lync Server 2013 might already have the required security infrastructure in place.</span></span> <span data-ttu-id="72197-123">Pour les entreprises recherchant des recommandations, Microsoft fournit une solution comme exemple de création d’une infrastructure informatique sécurisée.</span><span class="sxs-lookup"><span data-stu-id="72197-123">For enterprises looking for guidance, Microsoft provides solution as an example of how to build a secure IT infrastructure.</span></span> <span data-ttu-id="72197-124">Toutefois, cela ne signifie pas qu’il s’agit de la seule solution et qu’elle n’implique pas qu’il s’agit de la solution préférée pour Lync Server.</span><span class="sxs-lookup"><span data-stu-id="72197-124">However, this does not imply that it is the only solution, nor does it imply that it is the preferred solution for Lync Server.</span></span> <span data-ttu-id="72197-125">Nous recommandons aux clients d’entreprise de choisir une solution adaptée à leurs besoins spécifiques en fonction de leur infrastructure de sécurité informatique et de leurs besoins. L’exemple de solution Microsoft utilise IPSec et la stratégie de groupe pour l’isolement du serveur et du domaine.</span><span class="sxs-lookup"><span data-stu-id="72197-125">We recommend that enterprise customers choose the solution suits their specific needs, based on their IT security infrastructure and requirements.The example Microsoft solution employs IPSec and Group Policy for Server and Domain Isolation.</span></span> <span data-ttu-id="72197-126">Pour plus d’informations [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544), reportez-vous à.</span><span class="sxs-lookup"><span data-stu-id="72197-126">For details, see [http://go.microsoft.com/fwlink/p/?LinkId=268544](http://go.microsoft.com/fwlink/p/?linkid=268544).</span></span> <span data-ttu-id="72197-127">Pour des questions et des commentaires, contactez secwish@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="72197-127">For questions and comments, contact secwish@microsoft.com.</span></span>

<span data-ttu-id="72197-128">Une autre solution possible consiste à utiliser IPSec simplement pour sécuriser les données envoyées par le service de sauvegarde proprement dit.</span><span class="sxs-lookup"><span data-stu-id="72197-128">Another possible solution is to use IPSec just to help secure the data sent by the Backup Service itself.</span></span> <span data-ttu-id="72197-129">Si vous choisissez cette méthode, vous devez configurer les règles IPSec du protocole SMB pour les serveurs ci-dessous, où le pool A et le pool B sont deux pools frontaux associés.</span><span class="sxs-lookup"><span data-stu-id="72197-129">If you choose this method, you should configure the IPSec rules for the SMB protocol for the following servers, where Pool A and Pool B are two paired Front End pools.</span></span>

  - <span data-ttu-id="72197-130">Service SMB (TCP/445) de chaque serveur frontal dans le pool A vers le magasin de fichiers utilisé par le pool B.</span><span class="sxs-lookup"><span data-stu-id="72197-130">The SMB Service (TCP/445) from each Front End Server in Pool A to the File Store used by Pool B.</span></span>

  - <span data-ttu-id="72197-131">Service SMB (TCP/445) de chaque serveur frontal dans le pool B vers le magasin de fichiers utilisé par le pool A.</span><span class="sxs-lookup"><span data-stu-id="72197-131">The SMB Service (TCP/445) from each Front End Server in Pool B to the File Store used by Pool A.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="72197-132">IPsec n’est pas destiné à remplacer la sécurité au niveau de l’application, comme SSL/TLS.</span><span class="sxs-lookup"><span data-stu-id="72197-132">IPsec is not intended as a replacement for application-level security, such as SSL/TLS.</span></span> <span data-ttu-id="72197-133">L’intérêt d’utiliser IPsec est qu’il peut assurer la sécurité du trafic réseau pour les applications existantes sans avoir à les modifier.</span><span class="sxs-lookup"><span data-stu-id="72197-133">One advantage of using IPsec is that it can provide network traffic security for existing applications without having to change them.</span></span> <span data-ttu-id="72197-134">Les entreprises qui veulent simplement sécuriser le transport entre les deux centres de données doivent s’adresser à leurs fournisseurs de matériel réseau respectifs pour savoir comment configurer des connexions de réseau étendu (WAN) sécurisées avec leur matériel.</span><span class="sxs-lookup"><span data-stu-id="72197-134">Enterprises that want to just secure the transport between the two data centers should consult their respective networking hardware vendors about ways to set up secure WAN connections by using the vendor’s equipment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

