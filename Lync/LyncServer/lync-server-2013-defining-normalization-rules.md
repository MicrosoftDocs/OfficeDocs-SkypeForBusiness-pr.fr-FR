---
title: 'Lync Server 2013 : définition des règles de normalisation'
description: 'Lync Server 2013 : définition des règles de normalisation.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining normalization rules
ms:assetid: ed31d56c-00b5-4f72-bd9f-beb4100d441f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399071(v=OCS.15)
ms:contentKeyID: 48185741
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a123e17b1d3256781ff34e4cade2b344ba8fe14
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542040"
---
# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="95a54-103">Définition de règles de normalisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95a54-103">Defining normalization rules in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95a54-104">_**Dernière modification de la rubrique :** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="95a54-104">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="95a54-105">Les règles de normalisation Lync Server 2013 utilisent des expressions régulières .NET Framework pour convertir les numéros de téléphone composés au format E. 164 ; en d’autres termes, les règles de normalisation prennent le numéro de téléphone composé par un utilisateur et convertissent ce nombre au format utilisé en interne par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="95a54-105">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="95a54-106">Une ou plusieurs règles de normalisation doivent être affectées à chaque plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="95a54-106">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="95a54-107">Pour plus d’informations sur les règles de normalisation, voir [Dial plans and Normalization Rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="95a54-107">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="95a54-108">Pour plus d’informations sur la façon d’écrire des expressions régulières, voir « .NET Framework regular expressions » à l’adresse [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927) .</span><span class="sxs-lookup"><span data-stu-id="95a54-108">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [https://go.microsoft.com/fwlink/p/?linkId=140927](https://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="95a54-109">Vous pouvez utiliser l’une des méthodes suivantes pour définir ou modifier une règle de normalisation :</span><span class="sxs-lookup"><span data-stu-id="95a54-109">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="95a54-110">Utilisez l’outil de **création d’une règle de normalisation** pour spécifier des valeurs pour les chiffres de début, la longueur, les chiffres à supprimer et les chiffres à ajouter, puis laissez le panneau de configuration Lync Server générer le modèle de correspondance et la règle de traduction correspondants pour vous.</span><span class="sxs-lookup"><span data-stu-id="95a54-110">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="95a54-111">Écrivez les expressions régulières manuellement pour définir le modèle correspondant et la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="95a54-111">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="95a54-112">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="95a54-112">In This Section</span></span>

  - [<span data-ttu-id="95a54-113">Création ou modification d’une règle de normalisation à l’aide de la création d’une règle de normalisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95a54-113">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="95a54-114">Création ou modification manuelle d’une règle de normalisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95a54-114">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="95a54-115">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="95a54-115">See Also</span></span>


[<span data-ttu-id="95a54-116">Création d’un plan de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95a54-116">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="95a54-117">Modifier un plan de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95a54-117">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

