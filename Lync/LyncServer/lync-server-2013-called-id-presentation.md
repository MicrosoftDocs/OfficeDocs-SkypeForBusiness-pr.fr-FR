---
title: 'Lync Server 2013: appelé présentation ID'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 30bd84e60118697c94aba6c6088de68fc37d34c1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838687"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="c9582-102">Appelée présentation ID dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9582-102">Called ID presentation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9582-103">_**Dernière modification de la rubrique:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="c9582-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="c9582-104">Avec Lync Server 2010, le numéro de téléphone de la personne appelé (c’est-à-dire, le numéro de téléphone appelé) peut être converti à partir du format E. 164 vers le format de numérotation local requis par le Trunk pair (c’est-à-dire, la passerelle associée, le PBX (PBX) ou le Trunk SIP).</span><span class="sxs-lookup"><span data-stu-id="c9582-104">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="c9582-105">À cet effet, vous devez définir une ou plusieurs règles de traduction pour convertir l’URI de demande avant de l’acheminer vers l’homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="c9582-105">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c9582-106">La possibilité d’associer une ou plusieurs règles de traduction à une configuration de Trunk vocale d’entreprise est conçue pour être utilisée comme <EM>alternative</EM> à la configuration de règles de traduction sur l’homologue de Trunk.</span><span class="sxs-lookup"><span data-stu-id="c9582-106">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer.</span></span> <span data-ttu-id="c9582-107">N’associez pas de règles de traduction à une configuration de Trunk vocale d’entreprise si vous avez configuré des règles de traduction sur le Trunk homologue, car les deux règles peuvent entrer en conflit.</span><span class="sxs-lookup"><span data-stu-id="c9582-107">Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="c9582-108">Pour créer ou modifier une règle de traduction, vous pouvez utiliser l’une des méthodes suivantes:</span><span class="sxs-lookup"><span data-stu-id="c9582-108">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="c9582-109">Utilisez l’outil **créer une règle de traduction** pour spécifier des valeurs pour les chiffres de début, la longueur, les chiffres à supprimer et les chiffres à ajouter, puis laissez le panneau de configuration de Lync Server générer le modèle correspondant et la règle de traduction correspondants.</span><span class="sxs-lookup"><span data-stu-id="c9582-109">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="c9582-110">Rédigez manuellement des expressions régulières pour définir les modèles correspondants et les règles de traduction.</span><span class="sxs-lookup"><span data-stu-id="c9582-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9582-111">Pour plus d’informations sur la façon d’écrire des expressions régulières, voir «expressions <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>régulières .NET Framework» à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="c9582-111">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="http://go.microsoft.com/fwlink/p/?linkid=140927">http://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c9582-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="c9582-112">In This Section</span></span>

  - [<span data-ttu-id="c9582-113">Créer ou modifier une règle de traduction à l’aide de l’outil créer une règle de traduction dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9582-113">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="c9582-114">Créer ou modifier une règle de traduction manuellement dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9582-114">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c9582-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="c9582-115">See Also</span></span>


[<span data-ttu-id="c9582-116">Présentation de l’identification de l’appelant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9582-116">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

