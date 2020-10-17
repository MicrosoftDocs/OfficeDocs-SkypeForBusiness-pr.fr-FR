---
title: 'Lync Server 2013 : prise en charge et configuration requise pour les serveurs supplémentaires'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional server support and requirements
ms:assetid: 7622986b-abd6-4f45-8b5b-d5e2368521e8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398577(v=OCS.15)
ms:contentKeyID: 48184535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd3dad53b954fed8e1513ff9704b35c3c4831ffd
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521251"
---
# <a name="additional-server-support-and-requirements-in-lync-server-2013"></a><span data-ttu-id="824d1-102">Prise en charge supplémentaire des serveurs et configuration requise dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="824d1-102">Additional server support and requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="824d1-103">_**Dernière modification de la rubrique :** 2013-12-09_</span><span class="sxs-lookup"><span data-stu-id="824d1-103">_**Topic Last Modified:** 2013-12-09_</span></span>

<span data-ttu-id="824d1-104">En plus de la prise en charge logicielle décrite dans les autres sections de cette documentation de prise en charge, Lync Server 2013 présente les limitations de prise en charge suivantes :</span><span class="sxs-lookup"><span data-stu-id="824d1-104">In addition to the software support described in the other sections of this Supportability documentation, Lync Server 2013 has the following support limitations:</span></span>

  - <span data-ttu-id="824d1-105">Lync Server 2013 prend en charge le système DNS (Domain Name System) et l’équilibrage de la charge matérielle pour des rôles serveur spécifiques.</span><span class="sxs-lookup"><span data-stu-id="824d1-105">Lync Server 2013 supports Domain Name System (DNS) and hardware load balancing for specific server roles.</span></span> <span data-ttu-id="824d1-106">Il prend également en charge l’équilibrage de la charge d’application, le cas échéant.</span><span class="sxs-lookup"><span data-stu-id="824d1-106">It also supports application load balancing for Mediation Servers, where appropriate.</span></span> <span data-ttu-id="824d1-107">Pour plus d’informations pour savoir quand les utiliser, voir la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="824d1-107">For details about when to use each, see the Planning documentation.</span></span>

  - <span data-ttu-id="824d1-108">Lync Server 2013 utilise le protocole DLX (distribution list expansion Protocol) pour développer les listes de distribution.</span><span class="sxs-lookup"><span data-stu-id="824d1-108">Lync Server 2013 uses the Distribution List Expansion Protocol (DLX) to expand distribution lists.</span></span> <span data-ttu-id="824d1-109">Ce protocole spécifie également la méthode de service web utilisée pour récupérer l’appartenance d’une liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="824d1-109">This protocol also specifies the web service method that is used to get the membership of a distribution list.</span></span> <span data-ttu-id="824d1-110">Microsoft Exchange Server prend en charge les groupes dynamiques qui n’ont pas de membres attribués de façon statique.</span><span class="sxs-lookup"><span data-stu-id="824d1-110">Microsoft Exchange Server supports dynamic groups that do not have members statically assigned to them.</span></span> <span data-ttu-id="824d1-111">Au lieu de cela, ils stockent les demandes qui sont évaluées quand le groupe est développé.</span><span class="sxs-lookup"><span data-stu-id="824d1-111">Instead, they store queries that are evaluated when the group is expanded.</span></span> <span data-ttu-id="824d1-112">Le protocole DLX ne prend pas en charge les listes de distribution dynamiques.</span><span class="sxs-lookup"><span data-stu-id="824d1-112">DLX does not support dynamic distribution lists.</span></span> <span data-ttu-id="824d1-113">Cette limitation DLX s’applique à toutes les versions de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="824d1-113">This DLX limitation applies to all versions of Lync Server.</span></span>

  - <span data-ttu-id="824d1-114">L’Assistant Activer un utilisateur ne prend pas en charge la conversion automatique de caractères non anglais en URI compatible SIP, vous devez donc modifier l’adresse SIP manuellement.</span><span class="sxs-lookup"><span data-stu-id="824d1-114">The Enable User Wizard does not support automatic conversion of non-English characters to a SIP-compliant URI, so you must modify the SIP address manually.</span></span>

  - <span data-ttu-id="824d1-115">Pour les serveurs exécutant un logiciel antivirus, consultez la rubrique [exclusions d’analyse antivirus pour Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) pour obtenir les exclusions de virus suggérées et d’autres recommandations relatives à la sécurité.</span><span class="sxs-lookup"><span data-stu-id="824d1-115">For servers running antivirus software, refer to [Antivirus scanning exclusions for Lync Server 2013](lync-server-2013-antivirus-scanning-exclusions.md) for suggested virus exclusions and other security related recommendations.</span></span>

  - <span data-ttu-id="824d1-116">Si vous utilisez le protocole IPSec, nous vous recommandons de le désactiver sur les plages de ports utilisées pour le trafic audio et vidéo.</span><span class="sxs-lookup"><span data-stu-id="824d1-116">If you use IPsec, we recommend disabling IPsec over the port ranges used for audio and video traffic.</span></span> <span data-ttu-id="824d1-117">Pour plus d’informations, reportez-vous à la rubrique [IPSec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="824d1-117">For details, see [IPsec exceptions in Lync Server 2013](lync-server-2013-ipsec-exceptions.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="824d1-118">Si votre organisation utilise une infrastructure de qualité de service (QoS), le sous-système multimédia est compatible avec cette infrastructure.</span><span class="sxs-lookup"><span data-stu-id="824d1-118">If your organization uses a Quality of Service (QoS) infrastructure, the media subsystem is designed to work within this existing infrastructure.</span></span> <span data-ttu-id="824d1-119">Pour plus d’informations sur l’implémentation de la qualité de service, consultez la rubrique [Managing Quality of service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) dans la documentation des opérations.</span><span class="sxs-lookup"><span data-stu-id="824d1-119">For details about implementing QoS, see [Managing Quality of Service (QoS) in Lync Server 2013](lync-server-2013-managing-quality-of-service-qos.md) in the Operations documentation.</span></span>

  - <span data-ttu-id="824d1-120">L’utilisation du pare-feu du système d’exploitation est prise en charge.</span><span class="sxs-lookup"><span data-stu-id="824d1-120">Use of the operating system firewall is supported.</span></span> <span data-ttu-id="824d1-121">Lync Server 2013 gère les exceptions de pare-feu pour le pare-feu du système d’exploitation, à l’exception du logiciel de base de données Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="824d1-121">Lync Server 2013 manages the firewall exceptions for the operating system firewall, except for Microsoft SQL Server database software.</span></span> <span data-ttu-id="824d1-122">Pour plus d’informations sur la configuration requise en matière de pare-feu SQL Server, voir la documentation SQL Server.</span><span class="sxs-lookup"><span data-stu-id="824d1-122">For details about SQL Server firewall requirements, see the SQL Server documentation.</span></span>

  - <span data-ttu-id="824d1-123">Les interfaces externes utilisées pour implémenter la prise en charge de l’accès des utilisateurs externes doivent se trouver sur un sous-réseau distinct, et *pas* sur le même réseau que les interfaces internes.</span><span class="sxs-lookup"><span data-stu-id="824d1-123">The external interfaces used to implement support for external user access must be on a separate subnet, *not* on the same network as the internal interfaces.</span></span>

  - <span data-ttu-id="824d1-p106">La fonctionnalité XMPP de Lync Server 2013 est testée et prise en charge par Microsoft pour la fédération de messagerie instantanée avec Google Talk. Pour d’autres systèmes XMPP, contactez le fournisseur tier pour vérifier qu’il prend en charge la fédération avec Lync Server 2013 et pour obtenir d’autres recommandations de déploiement et de dépannage.</span><span class="sxs-lookup"><span data-stu-id="824d1-p106">The XMPP capability of Lync Server 2013 is tested and supported by Microsoft for instant messaging federation with Google Talk. For any other XMPP systems contact the third-party vendor to verify that they support federation with Lync Server 2013, and for any deployment or troubleshooting recommendations.</span></span>

  - <span data-ttu-id="824d1-126">Avec la publication des mises à jour cumulatives Lync Server 2013 : juillet 2013, Lync Server 2013 prend désormais en charge l’authentification à deux facteurs.</span><span class="sxs-lookup"><span data-stu-id="824d1-126">With the release of Lync Server 2013 Cumulative Updates: July 2013, Lync Server 2013 now supports two-factor authentication.</span></span> <span data-ttu-id="824d1-127">Pour plus d’informations, reportez-vous à la rubrique [authentification à deux facteurs dans Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="824d1-127">For more information, see [Two-factor authentication in Lync Server 2013](lync-server-2013-planning-for-and-deploying-two-factor-authentication.md).</span></span>

  - <span data-ttu-id="824d1-128">La plupart des serveurs internes nécessitent un type de certificat défini en tant qu' **authentification ouverte** (OAuth).</span><span class="sxs-lookup"><span data-stu-id="824d1-128">Most internal servers require a certificate type defined as **Open Authentication** (OAuth).</span></span> <span data-ttu-id="824d1-129">Vous devez demander et affecter un certificat OAuth lors de la **demande, installer et affecter des certificats** de l’Assistant Déploiement de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="824d1-129">You are required to request and assign an OAuth certificate during the **Request, Install and Assign Certificates** phase of the Lync Server Deployment Wizard.</span></span> <span data-ttu-id="824d1-130">La taille minimale d’une clé de certificat OAuth est de 1024 bits.</span><span class="sxs-lookup"><span data-stu-id="824d1-130">The minimum size for an OAuth certificate key is 1024 bits.</span></span> <span data-ttu-id="824d1-131">Un avertissement peut s’afficher si vous demandez un certificat dont la longueur de clé est inférieure à 2048 bits.</span><span class="sxs-lookup"><span data-stu-id="824d1-131">A warning may be displayed if you request a certificate with a key length less than 2048 bits in length.</span></span> <span data-ttu-id="824d1-132">Pour éviter des problèmes potentiels au cas où une longueur de clé de 2048 est appliquée au lieu d’être prévenu, il est vivement recommandé d’utiliser toujours une longueur de clé de 2048 pour les certificats OAuth.</span><span class="sxs-lookup"><span data-stu-id="824d1-132">To avoid potential problems in the event that a key length of 2048 is enforced instead of warned, it is strongly recommended to always use a key length of 2048 for OAuth certificates.</span></span>

  - <span data-ttu-id="824d1-133">Lync Server 2013 et Microsoft Exchange Server 2010 Service Pack 1 (SP1) fonctionnent avec la prise en charge des algorithmes de norme FIPS (Federal Information Processing Standard) 140-2 si les systèmes d’exploitation Windows Server 2008 R2 sont configurés pour utiliser les algorithmes FIPS 140-2 pour la cryptographie système.</span><span class="sxs-lookup"><span data-stu-id="824d1-133">Lync Server 2013 and Microsoft Exchange Server 2010 Service Pack 1 (SP1) operate with support for Federal Information Processing Standard (FIPS) 140-2 algorithms if the Windows Server 2008 R2 operating systems are configured to use the FIPS 140-2 algorithms for system cryptography.</span></span> <span data-ttu-id="824d1-134">Pour implémenter la prise en charge du cryptage FIPS, vous devez configurer chaque serveur exécutant Lync Server 2013 afin de le prendre en charge.</span><span class="sxs-lookup"><span data-stu-id="824d1-134">To implement FIPS support, you must configure each server running Lync Server 2013 to support it.</span></span> <span data-ttu-id="824d1-135">Pour plus d’informations sur les algorithmes compatibles FIPS et sur l’implémentation de la prise en charge du FIPS, consultez l’article 811833 de la base de connaissances Microsoft « chiffrement du système : utiliser des algorithmes compatibles FIPS pour le chiffrement, le hachage et la signature » dans Windows XP et les versions ultérieures de Windows à l’adresse [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833) .</span><span class="sxs-lookup"><span data-stu-id="824d1-135">For details about FIPS-compliant algorithms and how to implement FIPS support, see Microsoft Knowledge Base article 811833, "System cryptography: Use FIPS compliant algorithms for encryption, hashing, and signing security setting in Windows XP and in later versions of Windows at [https://go.microsoft.com/fwlink/p/?linkid=3052\&kbid=811833](https://go.microsoft.com/fwlink/p/?linkid=3052%26kbid=811833).</span></span> <span data-ttu-id="824d1-136">Pour plus d’informations sur la prise en charge et les limitations du FIPS 140-2 dans Exchange 2010, voir « algorithmes de prise en charge des algorithmes compatibles FIPS dans Exchange 2010 SP1 » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335) .</span><span class="sxs-lookup"><span data-stu-id="824d1-136">For details about FIPS 140-2 support and limitations in Exchange 2010, see "Exchange 2010 SP1 and Support for FIPS Compliant Algorithms" at [https://go.microsoft.com/fwlink/p/?linkId=205335](https://go.microsoft.com/fwlink/p/?linkid=205335).</span></span>

<span data-ttu-id="824d1-137">Lync Server 2013 nécessite l’installation d’autres logiciels sur des composants spécifiques avant ou pendant le déploiement.</span><span class="sxs-lookup"><span data-stu-id="824d1-137">Lync Server 2013 requires the installation of other software on specific components prior to or during deployment.</span></span> <span data-ttu-id="824d1-138">Cela inclut les logiciels disponibles avec le système d’exploitation, les logiciels téléchargeables et les logiciels installés automatiquement lors de l’installation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="824d1-138">This includes software that is available with the operating system, downloadable software, and software that is automatically installed during installation of Lync Server 2013.</span></span> <span data-ttu-id="824d1-139">Voici une liste de logiciels supplémentaires pouvant s’avérer nécessaires :</span><span class="sxs-lookup"><span data-stu-id="824d1-139">Following is a list of additional software that can be required:</span></span>

  - <span data-ttu-id="824d1-140">Windows Update</span><span class="sxs-lookup"><span data-stu-id="824d1-140">Windows Update</span></span>

  - <span data-ttu-id="824d1-141">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="824d1-141">Windows Identity Foundation</span></span>

  - <span data-ttu-id="824d1-142">Microsoft .NET 4,5 Framework</span><span class="sxs-lookup"><span data-stu-id="824d1-142">Microsoft .NET 4.5 Framework</span></span>

  - <span data-ttu-id="824d1-143">Microsoft Visual C++ 2012 Redistributable</span><span class="sxs-lookup"><span data-stu-id="824d1-143">Microsoft Visual C++ 2012 Redistributable</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="824d1-144">Microsoft Visual C++ 2012 Redistributable est automatiquement installé lors de l’installation de Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="824d1-144">Microsoft Visual C++ 2012 Redistributable is automatically installed when you install Lync Server 2013.</span></span> <span data-ttu-id="824d1-145">Vous ne devez pas installer et utiliser une autre version.</span><span class="sxs-lookup"><span data-stu-id="824d1-145">You should not install and use any other version.</span></span>

    
    </div>

  - <span data-ttu-id="824d1-146">Module de réécriture d’URL version 2.0 Redistribuable</span><span class="sxs-lookup"><span data-stu-id="824d1-146">URL Rewrite Module version 2.0 Redistributable</span></span>

  - <span data-ttu-id="824d1-147">Module d’exécution du format Windows Media</span><span class="sxs-lookup"><span data-stu-id="824d1-147">Windows Media Format Runtime</span></span>

  - <span data-ttu-id="824d1-148">Windows PowerShell version 3,0</span><span class="sxs-lookup"><span data-stu-id="824d1-148">Windows PowerShell version 3.0</span></span>

  - <span data-ttu-id="824d1-149">Plug-in de navigateur Microsoft Silverlight 4 (Silverlight 4.0.50524.0 ou dernière version du Panneau de configuration Lync Server)</span><span class="sxs-lookup"><span data-stu-id="824d1-149">Microsoft Silverlight 4 browser plug-in (Silverlight 4.0.50524.0 or the latest version for Lync Server Control Panel)</span></span>

  - <span data-ttu-id="824d1-150">Outils des services de domaine Active Directory</span><span class="sxs-lookup"><span data-stu-id="824d1-150">Active Directory Domain Services tools</span></span>

<span data-ttu-id="824d1-151">Certains de ces logiciels requis s’appliquent uniquement à des rôles serveur ou composants spécifiques.</span><span class="sxs-lookup"><span data-stu-id="824d1-151">Some of these software requirements only apply to specific server roles or components.</span></span> <span data-ttu-id="824d1-152">Pour plus d’informations sur la configuration logicielle requise, voir la rubrique relative à la [configuration logicielle requise pour Lync Server 2013](lync-server-2013-additional-software-requirements.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="824d1-152">For details about these software requirements, see [Additional software requirements for Lync Server 2013](lync-server-2013-additional-software-requirements.md) in the Planning documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

