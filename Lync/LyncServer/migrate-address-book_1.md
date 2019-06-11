---
title: Migrer le carnet d’adresses
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Address Book
ms:assetid: b6e000ce-8b2e-460c-8a8b-000254b9d778
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205198(v=OCS.15)
ms:contentKeyID: 48185218
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8dff13c31ecf203d6e6e4b60c22a3792475e403f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846178"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-address-book"></a><span data-ttu-id="a9e99-102">Migrer le carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="a9e99-102">Migrate Address Book</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a9e99-103">_**Dernière modification de la rubrique:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="a9e99-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="a9e99-104">**Pour migrer des règles de normalisation personnalisées du carnet d’adresses**</span><span class="sxs-lookup"><span data-stu-id="a9e99-104">**To migrate Address Book customized normalization rules**</span></span>

1.  <span data-ttu-id="a9e99-105">Recherchez le fichier\_.\_txt\_du numéro\_de téléphone de l’entreprise à la racine du dossier partagé du carnet d’adresses, puis copiez-le à la racine du dossier partagé du carnet d’adresses dans votre pool de pilotes 2013 de Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a9e99-105">Find the Company\_Phone\_Number\_Normalization\_Rules.txt file in the root of the Address Book shared folder, and copy it to the root of the Address Book shared folder in your Lync Server 2013 pilot pool.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a9e99-106">Les règles de normalisation de votre carnet d’adresses sont installées dans votre répertoire de fichiers de composants Web ABS.</span><span class="sxs-lookup"><span data-stu-id="a9e99-106">The sample Address Book normalization rules have been installed in your ABS Web component file directory.</span></span> <span data-ttu-id="a9e99-107">Le chemin d’accès est <STRONG>$installedDriveLetter: \Program Files\Microsoft Lync Server 2013 \ Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules. txt,</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a9e99-107">The path is <STRONG>$installedDriveLetter:\Program Files\Microsoft Lync Server 2013\Web Components\Address Book Files\Files\ Sample_Company_Phone_Number_Normalization_Rules.txt,</STRONG>.</span></span> <span data-ttu-id="a9e99-108">Ce fichier peut être copié et renommé &nbsp; <STRONG>Company_Phone_Number_Normalization_Rules. txt</STRONG> &nbsp;dans le répertoire racine du dossier partagé du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="a9e99-108">This file can be copied and renamed as &nbsp;<STRONG>Company_Phone_Number_Normalization_Rules.txt</STRONG> &nbsp;to the address book shared folder’s root directory.</span></span> <span data-ttu-id="a9e99-109">Par exemple, dans le carnet d’adresses <STRONG></STRONG>partagé dans&nbsp;$serverX, le chemin d’accès est semblable à ce qui suit: <STRONG> \\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="a9e99-109">For example, the address book shared in <STRONG>$serverX</STRONG>,&nbsp;the path will be similar to: <STRONG>\\$serverX \LyncFileShare\2-WebServices-1\ABFiles</STRONG>.</span></span>

    
    </div>

2.  <span data-ttu-id="a9e99-110">Utilisez un éditeur de texte, tel que le bloc-notes,\_pour\_ouvrir\_le fichier\_de règles de normalisation des numéros de téléphone de l’entreprise.</span><span class="sxs-lookup"><span data-stu-id="a9e99-110">Use a text editor, such as Notepad, to open the Company\_Phone\_Number\_Normalization\_Rules.txt file.</span></span>

3.  <span data-ttu-id="a9e99-111">Certains types d’entrée ne fonctionnent pas correctement dans Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a9e99-111">Certain types of entries will not work correctly in Lync Server 2013.</span></span> <span data-ttu-id="a9e99-112">Parcourez le fichier pour obtenir les types d’entrée décrits dans cette étape, modifiez-les comme vous le souhaitez et enregistrez les modifications apportées au dossier partagé du carnet d’adresses dans votre pool de pilotes.</span><span class="sxs-lookup"><span data-stu-id="a9e99-112">Look through the file for the types of entries described in this step, edit them as necessary, and save the changes to the Address Book shared folder in your pilot pool.</span></span>
    
    <span data-ttu-id="a9e99-113">Les chaînes qui comprennent des espaces blancs ou des signes de ponctuation peuvent entraîner l’échec des règles de normalisation, car ces caractères sont supprimés de la chaîne qui est en entrée dans les règles de normalisation.</span><span class="sxs-lookup"><span data-stu-id="a9e99-113">Strings that include required whitespace or punctuation cause normalization rules to fail because these characters are stripped out of the string that is input to the normalization rules.</span></span> <span data-ttu-id="a9e99-114">Si vous avez des chaînes qui incluent des espaces blancs ou des signes de ponctuation requis, vous devez modifier les chaînes.</span><span class="sxs-lookup"><span data-stu-id="a9e99-114">If you have strings that include required whitespace or punctuation, you need to modify the strings.</span></span> <span data-ttu-id="a9e99-115">Par exemple, la chaîne suivante entraînera l’échec de la règle de normalisation:</span><span class="sxs-lookup"><span data-stu-id="a9e99-115">For example, the following string would cause the normalization rule to fail:</span></span>
    
        \s*\(\s*\d\d\d\s*\)\s*\-\s*\d\d\d\s*\-\s*\d\d\d\d
    
    <span data-ttu-id="a9e99-116">La chaîne suivante n’entraînera pas l’échec de la règle de normalisation:</span><span class="sxs-lookup"><span data-stu-id="a9e99-116">The following string would not cause the normalization rule to fail:</span></span>
    
        \s*\(?\s*\d\d\d\s*\)?\s*\-?\s*\d\d\d\s*\-?\s*\d\d\d\d

</div>

<span> </span>

</div>

</div>

</div>

