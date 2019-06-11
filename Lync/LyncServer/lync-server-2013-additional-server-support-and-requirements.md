---
title: 'Lync Server 2013 : Autres prises en charge et configurations de serveur requises'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29f2d1a1b728fcec84f0aed70f00f1143c70c490
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838925"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="1b58a-102">Autres prises en charge et configurations de serveur requises dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1b58a-102">Additional server support and requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1b58a-103">_**Dernière modification de la rubrique:** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="1b58a-103">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="1b58a-104">Outre la prise en charge logicielle décrite dans les autres sections de cette documentation sur la prise en charge, Lync Server 2013 présente les limites de support suivantes:</span><span class="sxs-lookup"><span data-stu-id="1b58a-104">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="1b58a-105">Lync Server 2013 prend en charge le système de nom de domaine (DNS) et l’équilibrage de charge matérielle pour des rôles de serveur spécifiques.</span><span class="sxs-lookup"><span data-stu-id="1b58a-105">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="1b58a-106">Il prend également en charge l’équilibrage de charge des applications pour les serveurs de médiation, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="1b58a-106">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="1b58a-107">Pour plus d’informations sur les situations d’utilisation, consultez la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="1b58a-107">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="1b58a-108">Lync Server 2013 utilise le protocole DLX (distribution de liste de distribution) pour développer des listes de distribution.</span><span class="sxs-lookup"><span data-stu-id="1b58a-108">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="1b58a-109">Ce protocole spécifie également la méthode de service Web qui est utilisée pour obtenir l’appartenance d’une liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="1b58a-109">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="1b58a-110">Microsoft Exchange Server prend en charge les groupes dynamiques qui n’ont pas de membres attribués de manière statique.</span><span class="sxs-lookup"><span data-stu-id="1b58a-110">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="1b58a-111">Au lieu de cela, il stocke les requêtes évaluées lors du développement du groupe.</span><span class="sxs-lookup"><span data-stu-id="1b58a-111">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="1b58a-112">DLX ne prend pas en charge les listes de distribution dynamiques.</span><span class="sxs-lookup"><span data-stu-id="1b58a-112">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="1b58a-113">Cette limitation DLX s’applique à toutes les versions de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1b58a-113">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="1b58a-114">L’Assistant permettre aux utilisateurs ne prenant pas en charge la conversion automatique des caractères non anglais en un URI compatible SIP, vous devez modifier manuellement l’adresse SIP.</span><span class="sxs-lookup"><span data-stu-id="1b58a-114">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="1b58a-115">Pour les serveurs exécutant un logiciel antivirus, voir exclusions de [l’analyse antivirus pour Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) pour les exclusions de virus proposées et autres recommandations en matière de sécurité.</span><span class="sxs-lookup"><span data-stu-id="1b58a-115">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="1b58a-116">Si vous utilisez IPsec, nous vous recommandons de désactiver IPsec par rapport aux plages de port utilisées pour le trafic audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="1b58a-116">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="1b58a-117">Pour plus d’informations, reportez-vous à la section [exceptions IPSec dans Lync Server 2013](lync-server-2013-ipsec-exceptions.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="1b58a-117">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="1b58a-118">Si votre organisation utilise une infrastructure de qualité de service (QoS), le sous-système multimédia est compatible avec cette infrastructure.</span><span class="sxs-lookup"><span data-stu-id="1b58a-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="1b58a-119">Pour plus d’informations sur l’implémentation de QoS, voir [gestion de la qualité de service (QoS) dans Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="1b58a-119">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="1b58a-120">L’utilisation du pare-feu du système d’exploitation est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="1b58a-120">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="1b58a-121">Lync Server 2013 gère les exceptions de pare-feu pour le pare-feu du système d’exploitation, à l’exception du logiciel de base de données Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1b58a-121">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="1b58a-122">Pour plus d’informations sur la configuration requise pour le pare-feu SQL Server, voir la documentation SQL Server.</span><span class="sxs-lookup"><span data-stu-id="1b58a-122">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="1b58a-123">Les interfaces externes utilisées pour mettre en œuvre la prise en charge de l’accès des utilisateurs externes doivent se trouver sur un sous-réseau distinct et *non* sur le même réseau que les interfaces internes.</span><span class="sxs-lookup"><span data-stu-id="1b58a-123">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="1b58a-p106">La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.</span><span class="sxs-lookup"><span data-stu-id="1b58a-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="1b58a-126">Avec la publication des mises à jour cumulatives de Lync Server 2013: juillet 2013, Lync Server 2013 prend désormais en charge l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="1b58a-126">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="1b58a-127">Pour plus d’informations, reportez-vous à la rubrique [authentification à deux facteurs dans Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="1b58a-127">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="1b58a-128">La plupart des serveurs internes nécessitent un type de certificat défini comme **authentification d’ouverture** (OAuth).</span><span class="sxs-lookup"><span data-stu-id="1b58a-128">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="1b58a-129">Vous devez demander et attribuer un certificat OAuth lors de la phase de **demande, d’installation et d’attribution des certificats** de l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1b58a-129">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="1b58a-130">La taille minimale d’une clé de certificat OAuth est de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="1b58a-130">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="1b58a-131">Un avertissement risque de s’afficher si vous demandez un certificat dont la longueur de la clé est inférieure à 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="1b58a-131">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="1b58a-132">Pour éviter d’éventuels problèmes dans le cas où une longueur de clé de 2048 est appliquée au lieu d’être prévenu, il est vivement recommandé de toujours utiliser une longueur de clé d' 2048 pour les certificats OAuth.</span><span class="sxs-lookup"><span data-stu-id="1b58a-132">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="1b58a-133">Lync Server 2013 et Microsoft Exchange Server 2010 Service Pack 1 (SP1) prennent en charge les algorithmes 140-2 FIPS (Federal Information Processing Standard), si les systèmes d’exploitation Windows Server 2008 R2 sont configurés pour utiliser les algorithmes 140-2 FIPS pour cryptographie système.</span><span class="sxs-lookup"><span data-stu-id="1b58a-133">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="1b58a-134">Pour mettre en œuvre la prise en charge du FIPS, vous devez configurer chaque serveur exécutant Lync Server 2013 pour le prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="1b58a-134">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="1b58a-135">Pour plus d’informations sur les algorithmes compatibles FIPS et sur l’implémentation de la prise en charge du cryptage FIPS, voir l’article de la base de connaissances Microsoft 811833, «chiffrement de système: utiliser les algorithmes compatibles FIPS pour le paramètre de sécurité du chiffrement, du hachage et de la signature dans Windows XP et versions ultérieures. versions de Windows à [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833)l’adresse.</span><span class="sxs-lookup"><span data-stu-id="1b58a-135">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [http://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](http://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="1b58a-136">Pour plus d’informations sur la prise en charge et les limitations de FIPS 140-2 dans Exchange 2010, voir «Exchange 2010 SP1 et prise en [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335)charge des algorithmes compatibles FIPS» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="1b58a-136">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [http://go.microsoft.com/fwlink/p/?linkId=205335](http://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="1b58a-137">Lync Server 2013 nécessite l’installation d’autres logiciels sur des composants spécifiques avant ou lors du déploiement.</span><span class="sxs-lookup"><span data-stu-id="1b58a-137">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="1b58a-138">Cela inclut les logiciels disponibles avec le système d’exploitation, le logiciel téléchargeable et les logiciels qui sont automatiquement installés lors de l’installation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b58a-138">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="1b58a-139">Vous trouverez ci-dessous une liste de logiciels supplémentaires qui peuvent être nécessaires:</span><span class="sxs-lookup"><span data-stu-id="1b58a-139">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="1b58a-140">Windows Update</span><span class="sxs-lookup"><span data-stu-id="1b58a-140">Windows Update</span></span>

  - <span data-ttu-id="1b58a-141">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="1b58a-141">Windows Identity Foundation</span></span>

  - <span data-ttu-id="1b58a-142">Microsoft .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="1b58a-142">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="1b58a-143">Microsoft Visual C++ 2012 redistribuable</span><span class="sxs-lookup"><span data-stu-id="1b58a-143">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="1b58a-144">Microsoft Visual C++ 2012 redistribuable est automatiquement installé lors de l’installation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1b58a-144">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="1b58a-145">Vous ne devez pas installer et utiliser une autre version.</span><span class="sxs-lookup"><span data-stu-id="1b58a-145">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="1b58a-146">Module de réécriture d’URL version 2,0 redistribuable</span><span class="sxs-lookup"><span data-stu-id="1b58a-146">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="1b58a-147">Module d’exécution du format Windows Media</span><span class="sxs-lookup"><span data-stu-id="1b58a-147">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="1b58a-148">Windows PowerShell version 3,0</span><span class="sxs-lookup"><span data-stu-id="1b58a-148">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="1b58a-149">Plug-in Microsoft Silverlight 4 Browser (Silverlight 4.0.50524.0 ou la version la plus récente du panneau de configuration de Lync Server)</span><span class="sxs-lookup"><span data-stu-id="1b58a-149">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="1b58a-150">Outils de services de domaine Active Directory</span><span class="sxs-lookup"><span data-stu-id="1b58a-150">Active Directory Domain Services tools</span></span>

<span data-ttu-id="1b58a-151">Certaines de ces configurations logicielles s’appliquent uniquement aux rôles ou composants serveur spécifiques.</span><span class="sxs-lookup"><span data-stu-id="1b58a-151">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="1b58a-152">Pour plus d’informations sur la configuration logicielle requise, voir [configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="1b58a-152">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

