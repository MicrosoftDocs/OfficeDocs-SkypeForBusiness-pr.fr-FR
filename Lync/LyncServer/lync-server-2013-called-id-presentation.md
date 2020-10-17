---
title: 'Lync Server 2013 : présentation de l’ID appelée'
description: 'Lync Server 2013 : présentation de l’ID appelée.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Called ID presentation
ms:assetid: cf6c6af5-3418-411e-a50b-7a9cf8e100d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721892(v=OCS.15)
ms:contentKeyID: 49733826
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b438c7c19bc3c4ad641a8b9f8dac319c9fc2b1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565200"
---
# <a name="called-id-presentation-in-lync-server-2013"></a><span data-ttu-id="979d7-103">Présentation de l’ID appelée dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="979d7-103">Called ID presentation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="979d7-104">_**Dernière modification de la rubrique :** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="979d7-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="979d7-105">Avec Lync Server 2010, le numéro de téléphone de la partie appelée (c’est-à-dire, le numéro de téléphone appelé) peut être converti à partir du format E. 164 vers le format de numérotation local requis par l’homologue de jonction (c’est-à-dire, la passerelle associée, le PBX (Private Branch Exchange) ou la jonction SIP).</span><span class="sxs-lookup"><span data-stu-id="979d7-105">With Lync Server 2010, the called party’s phone number (that is, the phone number called) can be translated from E.164 format to the local dialing format that is required by the trunk peer (that is, the associated gateway, private branch exchange (PBX), or SIP trunk).</span></span> <span data-ttu-id="979d7-106">Pour ce faire, vous devez définir une ou plusieurs règles de traduction pour traduire l’URI de demande avant de l’acheminer vers l’homologue de jonction.</span><span class="sxs-lookup"><span data-stu-id="979d7-106">To do this, you must define one or more translation rules to translate the Request URI before routing it to the trunk peer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="979d7-p102">La possibilité d’associer une ou plusieurs règles de traduction à une configuration de jonction Voix Entreprise peut servir d’<EM>alternative</EM> à la définition de règles de traduction sur l’homologue de jonction. N’associez pas de règles de traduction avec une configuration de jonction Voix Entreprise si vous avez configuré les règles de traduction sur le pair de jonction, car les deux règles risqueraient de provoquer un conflit.</span><span class="sxs-lookup"><span data-stu-id="979d7-p102">The ability to associate one or more translation rules with an Enterprise Voice trunk configuration is intended to be used as an <EM>alternative</EM> to configuring translation rules on the trunk peer. Do not associate translation rules with an Enterprise Voice trunk configuration if you have configured translation rules on the trunk peer because the two rules might conflict.</span></span>



</div>

<span data-ttu-id="979d7-109">Vous pouvez employer l’une des méthodes suivantes pour créer ou modifier une règle de traduction :</span><span class="sxs-lookup"><span data-stu-id="979d7-109">You can use either of the following methods to create or modify a translation rule:</span></span>

  - <span data-ttu-id="979d7-110">Utilisez l’outil **créer une règle de traduction** pour spécifier des valeurs pour les chiffres de début, la longueur, les chiffres à supprimer et les chiffres à ajouter, puis laissez le panneau de configuration Lync Server générer le modèle de correspondance et la règle de traduction correspondants pour vous.</span><span class="sxs-lookup"><span data-stu-id="979d7-110">Use the **Build a Translation Rule** tool to specify values for the starting digits, length, digits to remove and digits to add, and then let Lync Server Control Panel generate the corresponding matching pattern and translation rule for you.</span></span>

  - <span data-ttu-id="979d7-111">Écrivez les expressions régulières manuellement pour définir le modèle correspondant et la règle de traduction.</span><span class="sxs-lookup"><span data-stu-id="979d7-111">Write regular expressions manually to define the matching pattern and translation rule.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="979d7-112">Pour plus d’informations sur la façon d’écrire des expressions régulières, voir « .NET Framework regular expressions » à l’adresse <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A> .</span><span class="sxs-lookup"><span data-stu-id="979d7-112">For information about how to write regular expressions, see ".NET Framework Regular Expressions" at <A href="https://go.microsoft.com/fwlink/p/?linkid=140927">https://go.microsoft.com/fwlink/p/?linkId=140927</A>.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="979d7-113">Dans cette section</span><span class="sxs-lookup"><span data-stu-id="979d7-113">In This Section</span></span>

  - [<span data-ttu-id="979d7-114">Création ou modification d’une règle de conversion à l’aide de l’outil créer une règle de traduction dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="979d7-114">Create or modify a translation rule by using the Build a Translation Rule tool in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-by-using-the-build-a-translation-rule-tool.md)

  - [<span data-ttu-id="979d7-115">Création ou modification manuelle d’une règle de traduction dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="979d7-115">Create or modify a translation rule manually in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-translation-rule-manually.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="979d7-116">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="979d7-116">See Also</span></span>


[<span data-ttu-id="979d7-117">Présentation de l’ID de l’appelant dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="979d7-117">Caller ID presentation in Lync Server 2013</span></span>](lync-server-2013-caller-id-presentation.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

