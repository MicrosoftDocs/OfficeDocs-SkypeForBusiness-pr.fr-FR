---
title: 'Lync Server 2013 : Définition de règles de normalisation'
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
ms.openlocfilehash: b75883d99d218d711e9d96de7ebfd7d360972a6a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-normalization-rules-in-lync-server-2013"></a><span data-ttu-id="0a926-102">Définition de règles de normalisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a926-102">Defining normalization rules in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0a926-103">_**Dernière modification de la rubrique :** 2014-04-22_</span><span class="sxs-lookup"><span data-stu-id="0a926-103">_**Topic Last Modified:** 2014-04-22_</span></span>

<span data-ttu-id="0a926-104">Les règles de normalisation de Lync Server 2013 utilisent des expressions régulières du .NET Framework pour convertir les numéros de téléphone numérotés au format E. 164. en d’autres termes, les règles de normalisation emportent le numéro de téléphone composé par un utilisateur et convertissent ce numéro au format utilisé en interne par Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0a926-104">Lync Server 2013 normalization rules use .NET Framework regular expressions to translate dialed phone numbers to E.164 format; in other words, normalization rules take the phone number dialed by a user and convert that number to the format used internally by Lync Server.</span></span> <span data-ttu-id="0a926-105">Une ou plusieurs règles de normalisation doivent être affectées à chaque plan de numérotation.</span><span class="sxs-lookup"><span data-stu-id="0a926-105">Each dial plan must be assigned one or more normalization rules.</span></span>

<span data-ttu-id="0a926-106">Pour plus d’informations sur les règles de normalisation, voir [plans de numérotation et règles de normalisation dans Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) dans la documentation de planification.</span><span class="sxs-lookup"><span data-stu-id="0a926-106">For details about normalization rules, see [Dial plans and normalization rules in Lync Server 2013](lync-server-2013-dial-plans-and-normalization-rules.md) in the Planning documentation.</span></span>

<span data-ttu-id="0a926-107">Pour plus d’informations sur la façon d’écrire des expressions régulières, voir « expressions [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927)régulières .NET Framework » à l’adresse.</span><span class="sxs-lookup"><span data-stu-id="0a926-107">For details about how to write regular expressions, see ".NET Framework Regular Expressions" at [http://go.microsoft.com/fwlink/p/?linkId=140927](http://go.microsoft.com/fwlink/p/?linkid=140927).</span></span>

<span data-ttu-id="0a926-108">Pour définir ou modifier une règle de normalisation, vous pouvez utiliser l’une des méthodes suivantes :</span><span class="sxs-lookup"><span data-stu-id="0a926-108">You can use either of the following methods to define or edit a normalization rule:</span></span>

  - <span data-ttu-id="0a926-109">Utiliser l’outil **créer une règle de normalisation** pour spécifier des valeurs pour les chiffres de début, la longueur, les chiffres à supprimer et les chiffres à ajouter, puis laisser le panneau de configuration de Lync Server générer le modèle correspondant et la règle de traduction correspondants.</span><span class="sxs-lookup"><span data-stu-id="0a926-109">Use the **Build a Normalization Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="0a926-110">Rédigez manuellement des expressions régulières pour définir les modèles correspondants et les règles de traduction.</span><span class="sxs-lookup"><span data-stu-id="0a926-110">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0a926-111">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="0a926-111">In This Section</span></span>

  - [<span data-ttu-id="0a926-112">Créer ou modifier une règle de normalisation à l’aide de l’application créer une règle de normalisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a926-112">Create or modify a normalization rule by using Build a Normalization Rule in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-by-using-build-a-normalization-rule.md)

  - [<span data-ttu-id="0a926-113">Création ou modification manuelle d’une règle de normalisation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a926-113">Create or modify a normalization rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-normalization-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0a926-114">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="0a926-114">See Also</span></span>


[<span data-ttu-id="0a926-115">Créer un plan de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a926-115">Create a dial plan in Lync Server 2013</span></span>](lync-server-2013-create-a-dial-plan.md)  
[<span data-ttu-id="0a926-116">Modification d’un plan de numérotation dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0a926-116">Modify a dial plan in Lync Server 2013</span></span>](lync-server-2013-modify-a-dial-plan.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

