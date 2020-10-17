---
title: 'Lync Server 2013 : vérification de la réplication de schéma'
description: 'Lync Server 2013 : vérification de la réplication de schéma.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 019cd06db05a9ba683767f550a712ef188b47508
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560170"
---
# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a><span data-ttu-id="c67cb-103">Vérification de la réplication de schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c67cb-103">Verifying Active Directory schema replication in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c67cb-104">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="c67cb-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="c67cb-105">Avant d’exécuter la préparation de la forêt, vérifiez manuellement que la partition de schéma a été répliquée.</span><span class="sxs-lookup"><span data-stu-id="c67cb-105">Before you run forest preparation, manually verify that the schema partition has been replicated.</span></span>

<div>

## <a name="to-manually-verify-schema-replication"></a><span data-ttu-id="c67cb-106">Pour vérifier manuellement la réplication de schéma</span><span class="sxs-lookup"><span data-stu-id="c67cb-106">To manually verify schema replication</span></span>

1.  <span data-ttu-id="c67cb-107">Ouvrez une session sur un contrôleur de domaine en tant que membre du groupe Administrateurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="c67cb-107">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="c67cb-108">Ouvrez l’éditeur ADSI en cliquant sur **Démarrer**, sur **Outils d’administration**, puis sur **Modification ADSI**.</span><span class="sxs-lookup"><span data-stu-id="c67cb-108">Open ADSI Edit by clicking **Start**, clicking **Administrative Tools**, and then clicking **ADSI Edit**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c67cb-109">Vous pouvez également exécuter <STRONG>adsiedit.msc</STRONG> à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="c67cb-109">Alternatively, you can run <STRONG>adsiedit.msc</STRONG> from the command line.</span></span>

    
    </div>

3.  <span data-ttu-id="c67cb-110">Dans l’arborescence de Microsoft Management Console (MMC), cliquez sur **Modification ADSI** si cette option n’a pas encore été sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="c67cb-110">In the Microsoft Management Console (MMC) tree, if it is not already selected, click **ADSI Edit**.</span></span>

4.  <span data-ttu-id="c67cb-111">Dans le menu **Action**, cliquez sur **Se connecter à**.</span><span class="sxs-lookup"><span data-stu-id="c67cb-111">On the **Action** menu, click **Connect to**.</span></span>

5.  <span data-ttu-id="c67cb-112">Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="c67cb-112">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>

6.  <span data-ttu-id="c67cb-113">Sous le conteneur de schéma, recherchez CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="c67cb-113">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="c67cb-114">Si cet objet existe et si la valeur de l’attribut **rangeUpper** est 1150 et si la valeur de l’attribut **rangeLower** est 3, cela signifie que le schéma a été mis à jour et répliqué avec succès.</span><span class="sxs-lookup"><span data-stu-id="c67cb-114">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="c67cb-115">Si cet objet n’existe pas ou si la valeur des attributs **rangeUpper** et **rangeLower** n’est pas spécifiée, cela signifie que le schéma n’a pas été modifié ou n’a pas été répliqué.</span><span class="sxs-lookup"><span data-stu-id="c67cb-115">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c67cb-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c67cb-116">See Also</span></span>


[<span data-ttu-id="c67cb-117">Exécution de la préparation du schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c67cb-117">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)  


[<span data-ttu-id="c67cb-118">Préparation du schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c67cb-118">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

