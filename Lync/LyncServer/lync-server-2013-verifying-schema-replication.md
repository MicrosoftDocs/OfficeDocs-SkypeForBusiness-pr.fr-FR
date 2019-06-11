---
title: 'Lync Server 2013 : Vérification de la réplication de schéma'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d115738a4f22cb7795c2eb5a00ac642fbe43fc77
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846328"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a><span data-ttu-id="db83c-102">Vérification de la réplication de schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db83c-102">Verifying Active Directory schema replication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db83c-103">_**Dernière modification de la rubrique:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="db83c-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="db83c-104">Avant de procéder à la préparation de la forêt, vérifiez manuellement que celle-ci a été répliquée.</span><span class="sxs-lookup"><span data-stu-id="db83c-104">Before you run forest preparation, manually verify that the schema partition has been replicated.</span></span>

<div>

## <a name="to-manually-verify-schema-replication"></a><span data-ttu-id="db83c-105">Pour vérifier manuellement la réplication de schéma</span><span class="sxs-lookup"><span data-stu-id="db83c-105">To manually verify schema replication</span></span>

1.  <span data-ttu-id="db83c-106">Ouvrez une session sur un contrôleur de domaine en tant que membre du groupe administrateurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="db83c-106">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="db83c-107">Ouvrez ADSI Edit en cliquant sur **Démarrer**, sur **Outils d’administration**, puis sur **modification ADSI**.</span><span class="sxs-lookup"><span data-stu-id="db83c-107">Open ADSI Edit by clicking **Start**, clicking **Administrative Tools**, and then clicking **ADSI Edit**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="db83c-108">Vous pouvez également exécuter adsied <STRONG>. msc</STRONG> à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="db83c-108">Alternatively, you can run <STRONG>adsiedit.msc</STRONG> from the command line.</span></span>

    
    </div>

3.  <span data-ttu-id="db83c-109">Dans l’arborescence Microsoft Management Console (MMC), si ce n’est pas déjà fait, cliquez sur **ADSI Edit**.</span><span class="sxs-lookup"><span data-stu-id="db83c-109">In the Microsoft Management Console (MMC) tree, if it is not already selected, click **ADSI Edit**.</span></span>

4.  <span data-ttu-id="db83c-110">Dans le menu **Action**, cliquez sur **Connexion**.</span><span class="sxs-lookup"><span data-stu-id="db83c-110">On the **Action** menu, click **Connect to**.</span></span>

5.  <span data-ttu-id="db83c-111">Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="db83c-111">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>

6.  <span data-ttu-id="db83c-112">Sous le conteneur de schéma, recherchez CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="db83c-112">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="db83c-113">Si cet objet existe et que la valeur de l’attribut **rangeUpper** est 1150 et que la valeur de l’attribut **rangeLower** est 3, le schéma a été correctement mis à jour et répliqué.</span><span class="sxs-lookup"><span data-stu-id="db83c-113">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="db83c-114">Si cet objet n’existe pas ou si les valeurs des attributs **rangeUpper** et **rangeLower** ne sont pas spécifiées, le schéma n’a pas été modifié ou n’a pas été répliqué.</span><span class="sxs-lookup"><span data-stu-id="db83c-114">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="db83c-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="db83c-115">See Also</span></span>


[<span data-ttu-id="db83c-116">Exécution de la préparation du schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db83c-116">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)  


[<span data-ttu-id="db83c-117">Préparation du schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db83c-117">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

