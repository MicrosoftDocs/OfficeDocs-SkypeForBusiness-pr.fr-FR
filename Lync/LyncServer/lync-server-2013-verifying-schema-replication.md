---
title: 'Lync Server 2013 : vérification de la réplication de schéma'
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
ms.openlocfilehash: 41cb48da1711cfa6eb29a90f19a9b6e42b110c52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a><span data-ttu-id="67864-102">Vérification de la réplication de schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67864-102">Verifying Active Directory schema replication in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="67864-103">_**Dernière modification de la rubrique :** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="67864-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="67864-104">Avant d’exécuter la préparation de la forêt, vérifiez manuellement que la partition de schéma a été répliquée.</span><span class="sxs-lookup"><span data-stu-id="67864-104">Before you run forest preparation, manually verify that the schema partition has been replicated.</span></span>

<div>

## <a name="to-manually-verify-schema-replication"></a><span data-ttu-id="67864-105">Pour vérifier manuellement la réplication de schéma</span><span class="sxs-lookup"><span data-stu-id="67864-105">To manually verify schema replication</span></span>

1.  <span data-ttu-id="67864-106">Ouvrez une session sur un contrôleur de domaine en tant que membre du groupe Administrateurs d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="67864-106">Log on to a domain controller as a member of the Enterprise Admins group.</span></span>

2.  <span data-ttu-id="67864-107">Ouvrez l’éditeur ADSI en cliquant sur **Démarrer**, sur **Outils d’administration**, puis sur **Modification ADSI**.</span><span class="sxs-lookup"><span data-stu-id="67864-107">Open ADSI Edit by clicking **Start**, clicking **Administrative Tools**, and then clicking **ADSI Edit**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="67864-108">Vous pouvez également exécuter <STRONG>adsiedit.msc</STRONG> à partir de la ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="67864-108">Alternatively, you can run <STRONG>adsiedit.msc</STRONG> from the command line.</span></span>

    
    </div>

3.  <span data-ttu-id="67864-109">Dans l’arborescence de Microsoft Management Console (MMC), cliquez sur **Modification ADSI** si cette option n’a pas encore été sélectionnée.</span><span class="sxs-lookup"><span data-stu-id="67864-109">In the Microsoft Management Console (MMC) tree, if it is not already selected, click **ADSI Edit**.</span></span>

4.  <span data-ttu-id="67864-110">Dans le menu **Action**, cliquez sur **Se connecter à**.</span><span class="sxs-lookup"><span data-stu-id="67864-110">On the **Action** menu, click **Connect to**.</span></span>

5.  <span data-ttu-id="67864-111">Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="67864-111">In the **Connection Settings** dialog box under **Select a well known Naming Context**, select **Schema**, and then click **OK**.</span></span>

6.  <span data-ttu-id="67864-112">Sous le conteneur de schéma, recherchez CN=ms-RTC-SIP-SchemaVersion.</span><span class="sxs-lookup"><span data-stu-id="67864-112">Under the schema container, search for CN=ms-RTC-SIP-SchemaVersion.</span></span> <span data-ttu-id="67864-113">Si cet objet existe et si la valeur de l’attribut **rangeUpper** est 1150 et si la valeur de l’attribut **rangeLower** est 3, cela signifie que le schéma a été mis à jour et répliqué avec succès.</span><span class="sxs-lookup"><span data-stu-id="67864-113">If this object exists, and the value of the **rangeUpper** attribute is 1150 and the value of the **rangeLower** attribute is 3, then the schema was successfully updated and replicated.</span></span> <span data-ttu-id="67864-114">Si cet objet n’existe pas ou si la valeur des attributs **rangeUpper** et **rangeLower** n’est pas spécifiée, cela signifie que le schéma n’a pas été modifié ou n’a pas été répliqué.</span><span class="sxs-lookup"><span data-stu-id="67864-114">If this object does not exist or the values of the **rangeUpper** and **rangeLower** attributes are not as specified, then the schema was not modified or has not replicated.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="67864-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="67864-115">See Also</span></span>


[<span data-ttu-id="67864-116">Exécution de la préparation du schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67864-116">Running Active Directory schema preparation in Lync Server 2013</span></span>](lync-server-2013-running-schema-preparation.md)  


[<span data-ttu-id="67864-117">Préparation du schéma Active Directory dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="67864-117">Preparing the Active Directory schema in Lync Server 2013</span></span>](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

