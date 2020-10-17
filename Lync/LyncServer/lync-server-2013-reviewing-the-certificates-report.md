---
title: 'Lync Server 2013 : analyse du rapport de certificats'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reviewing the Certificates Report
ms:assetid: 549cfc9b-3cc5-4483-a93c-fc0738c7f622
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558651(v=OCS.15)
ms:contentKeyID: 51541477
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78460666e588ca60249e0c9d8aed8b5870256445
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511341"
---
# <a name="reviewing-the-certificates-report-in-lync-server-2013"></a><span data-ttu-id="b497f-102">Consultation du rapport Certificates dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b497f-102">Reviewing the Certificates Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b497f-103">_**Dernière modification de la rubrique :** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="b497f-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="b497f-104">Le rapport Certificates contient tous les certificats requis dans le déploiement de Lync Server 2013 recommandé.</span><span class="sxs-lookup"><span data-stu-id="b497f-104">The Certificates Report contains all certificates that are required in the recommended Lync Server 2013 deployment.</span></span> <span data-ttu-id="b497f-105">Les comptes de l’outil de planification pour les noms de sujet et les autres noms de sujet entrés.</span><span class="sxs-lookup"><span data-stu-id="b497f-105">The Planning Tool accounts for the subject names and subject alternative names that are entered.</span></span> <span data-ttu-id="b497f-106">Le texte par défaut laissé non modifié peut représenter un défi potentiel pour l’équipe responsable de la demande et de l’émission des certificats.</span><span class="sxs-lookup"><span data-stu-id="b497f-106">Default text that is left unedited may represent a potential challenge for the team responsible for requesting and issuing the certificates.</span></span> <span data-ttu-id="b497f-107">Les informations de certificat contiennent également des données sur l’emplacement à partir duquel le certificat peut généralement être émis.</span><span class="sxs-lookup"><span data-stu-id="b497f-107">Certificate information also contains information about where the certificate can typically be issued from.</span></span> <span data-ttu-id="b497f-108">Si l’infrastructure ne dispose pas d’une PKI interne, tous les certificats peuvent être demandés par l’intermédiaire d’un fournisseur de certificats public.</span><span class="sxs-lookup"><span data-stu-id="b497f-108">If the infrastructure does not have an internal public key infrastructure (PKI) in place, all certificates can be requested through a public certificate provider.</span></span> <span data-ttu-id="b497f-109">Les champs EKU et Affecter à du rapport sont très utiles pour connaître ce que doivent être l’objectif et l’emplacement de chaque certificat.</span><span class="sxs-lookup"><span data-stu-id="b497f-109">Extended key usages (EKU) and Assign To fields in the report are very helpful in understanding what the purpose and location for each certificate should be.</span></span>

<span data-ttu-id="b497f-110">![Rapport d’administration des certificats](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Rapport d’administration des certificats")</span><span class="sxs-lookup"><span data-stu-id="b497f-110">![Certificates Admin Report](images/Gg558651.63a29335-d9e4-41ae-97ec-3c9d9fd30d8a(OCS.15).jpg "Certificates Admin Report")</span></span>

<span data-ttu-id="b497f-111">Examinez attentivement et assurez-vous de bien comprendre l’utilisation et l’objectif de chaque certificat dans le déploiement.</span><span class="sxs-lookup"><span data-stu-id="b497f-111">Carefully review, and be sure to understand, the use and purpose of each certificate in the deployment.</span></span> <span data-ttu-id="b497f-112">En cas de question sur le rôle d’un certificat, déterminez le serveur ou le service qui parle.</span><span class="sxs-lookup"><span data-stu-id="b497f-112">If there is a question about what a certificate does, determine which server or service is talking to what.</span></span> <span data-ttu-id="b497f-113">Les certificats dans Lync Server 2013 sont utilisés à deux fins principales :</span><span class="sxs-lookup"><span data-stu-id="b497f-113">Certificates in Lync Server 2013 are used for two primary purposes:</span></span>

  - <span data-ttu-id="b497f-114">Mutual Transport Layer Security (MTLS) : les ordinateurs impliqués dans la communication présentent chacun un certificat qui prouve leur identité sur un autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b497f-114">Mutual Transport Layer Security (MTLS) – The computers involved in the communication each present a certificate that proves their identity to another computer.</span></span> <span data-ttu-id="b497f-115">Il s’agit de l’authentification du serveur.</span><span class="sxs-lookup"><span data-stu-id="b497f-115">This is known as server authentication.</span></span> <span data-ttu-id="b497f-116">La communication ne peut pas commencer tant que chaque ordinateur n’approuve pas l’identité de l’autre ordinateur.</span><span class="sxs-lookup"><span data-stu-id="b497f-116">Communication cannot begin until each computer trusts the other computer’s identity.</span></span>

  - <span data-ttu-id="b497f-117">Chiffrement – Le chiffrement (Secure Sockets Layer ou SSL, et Transport Layer Security ou TLS) est un moyen très utile de sécuriser les communications, de garantir la confidentialité et de créer un système sûr de communication et de collaboration.</span><span class="sxs-lookup"><span data-stu-id="b497f-117">Encryption – Encryption (Secure Sockets Layer, or SSL, and Transport Layer Security, or TLS) is a critical means to help secure communications, help ensure privacy, and to create a trusted communications and collaboration system.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b497f-118">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="b497f-118">See Also</span></span>


[<span data-ttu-id="b497f-119">Examen des rapports de l’administrateur dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b497f-119">Reviewing the Administrator Reports in Lync Server 2013</span></span>](lync-server-2013-reviewing-the-administrator-reports.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

