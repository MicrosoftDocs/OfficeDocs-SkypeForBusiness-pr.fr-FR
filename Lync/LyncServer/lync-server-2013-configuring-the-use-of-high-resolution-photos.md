---
title: 'Lync Server 2013 : configuration de l’utilisation de photos haute résolution'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the use of high-resolution photos in Lync Server 2013
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49733753
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7d73970bd30aa72294369eac1d8206d19664230
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41996449"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-use-of-high-resolution-photos-in-microsoft-lync-server-2013"></a><span data-ttu-id="6f539-102">Configuration de l’utilisation de photos haute résolution dans Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f539-102">Configuring the use of high-resolution photos in Microsoft Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f539-103">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="6f539-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="6f539-104">Microsoft Lync Server 2010 offre aux utilisateurs la possibilité d’afficher des photos de leurs contacts (et de mettre à la disposition de leurs propres photos).</span><span class="sxs-lookup"><span data-stu-id="6f539-104">Microsoft Lync Server 2010 provided the ability for users to view photos of their contacts (and to make their own photos available to others).</span></span> <span data-ttu-id="6f539-105">En règle générale, ces photos ont été stockées dans le cadre de l’attribut thumbnailPhoto de l’utilisateur dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6f539-105">Typically these photos were stored as part of the user's thumbnailPhoto attribute in Active Directory.</span></span> <span data-ttu-id="6f539-106">Cela a permis de limiter sérieusement la taille et la résolution des photos : l’attribut thumbnailPhoto ne peut contenir qu’une photographie d’une taille maximale de 48 pixels par 48 pixels.</span><span class="sxs-lookup"><span data-stu-id="6f539-106">That placed a serious limitation on the size and resolution of the photos: the thumbnailPhoto attribute can only hold a photograph with a maximum size of 48 pixels by 48 pixels.</span></span>

<span data-ttu-id="6f539-107">Dans Microsoft Lync Server 2013, toutefois, les photos peuvent être stockées dans la boîte aux lettres 2013 de Microsoft Exchange Server d’un utilisateur ; Cela permet d’obtenir des photos d’une taille de 648 x 648 pixels.</span><span class="sxs-lookup"><span data-stu-id="6f539-107">In Microsoft Lync Server 2013, however, photos can be stored in a user's Microsoft Exchange Server 2013 mailbox; that allows for photo sizes up to 648 pixels by 648 pixels.</span></span> <span data-ttu-id="6f539-108">En outre, Exchange 2013 peut redimensionner automatiquement ces photos afin de les utiliser dans différents produits selon vos besoins.</span><span class="sxs-lookup"><span data-stu-id="6f539-108">In addition to that, Exchange 2013 can automatically resize these photos for use in different products as needed.</span></span> <span data-ttu-id="6f539-109">En règle générale, cela signifie trois tailles et résolutions de photos différentes :</span><span class="sxs-lookup"><span data-stu-id="6f539-109">Typically that means three different photo sizes and resolutions:</span></span>

  - <span data-ttu-id="6f539-110">48 pixels par 48 pixels, la taille utilisée pour l’attribut thumbnailPhoto Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6f539-110">48 pixels by 48 pixels, the size used for the Active Directory thumbnailPhoto attribute.</span></span> <span data-ttu-id="6f539-111">Si vous téléchargez une photo vers Exchange 2013, Exchange crée automatiquement une version de 48 pixel par 48 pixel de cette photo et met à jour l’attribut thumbnailPhoto de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6f539-111">If you upload a photo to Exchange 2013 Exchange will automatically create a 48 pixel by 48 pixel version of that photo and update the user's thumbnailPhoto attribute.</span></span> <span data-ttu-id="6f539-112">Notez toutefois que l’inverse n’est pas vrai : Si vous mettez à jour manuellement l’attribut thumbnailPhoto dans Active Directory, la photo dans la boîte aux lettres Exchange 2013 de l’utilisateur ne sera pas automatiquement mise à jour.</span><span class="sxs-lookup"><span data-stu-id="6f539-112">Note, however, that the reverse is not true: if you manually update the thumbnailPhoto attribute in Active Directory the photo in the user's Exchange 2013 mailbox will not automatically be updated.</span></span>

  - <span data-ttu-id="6f539-113">96 pixels par 96 pixels, pour une utilisation dans Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App et Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6f539-113">96 pixels by 96 pixels, for use in Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App, and Lync 2013.</span></span>

  - <span data-ttu-id="6f539-114">648 pixels par 648 pixels pour une utilisation dans Lync 2013 et Microsoft Lync Web App.</span><span class="sxs-lookup"><span data-stu-id="6f539-114">648 pixels by 648 pixels for use in Lync 2013 and Microsoft Lync Web App.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6f539-115">Si vous disposez des ressources, il est recommandé de télécharger des photos 648 x 648 ; Cela garantit une résolution maximale et une qualité d’image optimale dans n’importe quelle application Office 2013.</span><span class="sxs-lookup"><span data-stu-id="6f539-115">If you have the resources, it is recommended that you upload 648x648 photos; that provides the maximum resolution and optimal picture quality in any of the Office 2013 applications.</span></span> <span data-ttu-id="6f539-116">Chaque photo JPEG avec une taille de 648 x 648 et une profondeur de 24 bits aboutit à une taille de fichier d’environ 240 kilo-octets.</span><span class="sxs-lookup"><span data-stu-id="6f539-116">Each JPEG photo with a size of 648x648 and a depth of 24 bits results in a file size of approximately 240 kilobytes.</span></span> <span data-ttu-id="6f539-117">Cela signifie que vous aurez besoin d’environ 1 Mo d’espace disque pour chaque photo d’utilisateur de 4.</span><span class="sxs-lookup"><span data-stu-id="6f539-117">That means you will need approximately 1 megabyte of disk space for every 4 user photos.</span></span>



</div>

<span data-ttu-id="6f539-118">Les photos haute résolution, accessibles via les services Web Exchange, peuvent être téléchargées par les utilisateurs qui exécutent Outlook 2013 Web App ; les utilisateurs ne sont autorisés qu’à mettre à jour leur propre photo.</span><span class="sxs-lookup"><span data-stu-id="6f539-118">High-resolution photos, which are accessed by using Exchange Web Services, can be uploaded by users who are running Outlook 2013 Web App; users are only allowed to update their own photo.</span></span> <span data-ttu-id="6f539-119">Toutefois, les administrateurs peuvent mettre à jour la photo de n’importe quel utilisateur en utilisant l’environnement de commande Exchange Management Shell et une série de commandes Windows PowerShell semblables à ce qui suit :</span><span class="sxs-lookup"><span data-stu-id="6f539-119">Administrators, however, can update the photo for any user by using the Exchange Management Shell and a series of Windows PowerShell commands similar to the following:</span></span>

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="6f539-120">La première commande de l’exemple précédent utilise la cmdlet Get-Content pour lire le contenu du fichier C :\\photos\\kenmyer. jpg et stocker ces données dans une variable nommée $photo.</span><span class="sxs-lookup"><span data-stu-id="6f539-120">The first command in the preceding example uses the Get-Content cmdlet to read the contents of the file C:\\Photos\\Kenmyer.jpg and store that data in a variable named $photo.</span></span> <span data-ttu-id="6f539-121">Dans la seconde commande, l’applet de commande Exchange Set-applet userphoto est utilisée pour télécharger la photo et joindre cette photo au compte d’utilisateur de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="6f539-121">In the second command, the Exchange cmdlet Set-UserPhoto is used to upload the photo and attach that photo to Ken Myer's user account.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="6f539-122">Dans cet exemple, le nom d’affichage Active Directory de Ken Myer est utilisé comme identité du compte d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="6f539-122">In this example, Ken Myer's Active Directory display name is used as the user account Identity.</span></span> <span data-ttu-id="6f539-123">Vous pouvez également faire référence à un compte d’utilisateur à l’aide d’autres identificateurs, tels que l’adresse SMTP de l’utilisateur ou son nom d’utilisateur principal.</span><span class="sxs-lookup"><span data-stu-id="6f539-123">You can also reference a user account by using other identifiers such as the user's SMTP address or his or her User Principal Name.</span></span> <span data-ttu-id="6f539-124">Pour plus d’informations, reportez-vous <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> à la documentation de l’applet de commande Set-applet userphoto.</span><span class="sxs-lookup"><span data-stu-id="6f539-124">See the documentation for the Set-UserPhoto cmdlet at <A href="http://go.microsoft.com/fwlink/p/?linkid=268536">http://go.microsoft.com/fwlink/p/?LinkId=268536</A> for more information</span></span>



</div>

<span data-ttu-id="6f539-125">Le téléchargement de la photo n’équivaut pas à l’affectation de cette photo au compte d’utilisateur de Ken Myer.</span><span class="sxs-lookup"><span data-stu-id="6f539-125">Uploading the photo does not equate to assigning that photo to Ken Myer's user account.</span></span> <span data-ttu-id="6f539-126">Au lieu de cela, le téléchargement de la photo entraîne simplement l’affichage d’un aperçu de cette photo sur la page Options d’Outlook Web App.</span><span class="sxs-lookup"><span data-stu-id="6f539-126">Instead, uploading the photo simply results in a preview of that photo to be displayed on the Outlook Web App Options page.</span></span> <span data-ttu-id="6f539-127">Pour affecter réellement cette photo au compte d’utilisateur, l’utilisateur doit cliquer sur **Enregistrer** dans la page Options ou l’administrateur doit exécuter la troisième commande de l’exemple.</span><span class="sxs-lookup"><span data-stu-id="6f539-127">To actually assign that photo to the user account the user must click **Save** on the Options page or the administrator must execute the third command in the example.</span></span> <span data-ttu-id="6f539-128">Cette troisième commande utilise le paramètre Save pour affecter la photo au compte d’utilisateur de Ken Myer :</span><span class="sxs-lookup"><span data-stu-id="6f539-128">That third command uses the Save parameter to assign the photo to Ken Myer's user account:</span></span>

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

<span data-ttu-id="6f539-129">Pour vérifier que la nouvelle photo a été affectée au compte d’utilisateur, Ken Myer peut se connecter à Lync 2013, sélectionner des **options**, puis sélectionner **mon image**.</span><span class="sxs-lookup"><span data-stu-id="6f539-129">To verify that the new photo has been assigned to the user account, Ken Myer can log on to Lync 2013, select **Options**, and then select **My Picture**.</span></span> <span data-ttu-id="6f539-130">La photo téléchargée est affichée sous la forme photo personnelle de Ken.</span><span class="sxs-lookup"><span data-stu-id="6f539-130">The newly-uploaded photo should be displayed as Ken's personal photo.</span></span> <span data-ttu-id="6f539-131">Par ailleurs, les administrateurs peuvent vérifier la photo de n’importe quel utilisateur en démarrant Internet Explorer et en accédant à une URL semblable à celle-ci :</span><span class="sxs-lookup"><span data-stu-id="6f539-131">Alternatively, administrators can verify the photo for any user by starting Internet Explorer and navigating to a URL similar to this:</span></span>

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

<span data-ttu-id="6f539-132">Si l’administrateur peut afficher la photo à l’aide d’Internet Explorer, mais que l’utilisateur ne peut pas afficher sa photo dans Lync 2013, cela indique généralement un problème de connectivité avec les services Web Exchange ou avec le service de découverte automatique Exchange.</span><span class="sxs-lookup"><span data-stu-id="6f539-132">If the administrator can view the photo using Internet Explorer but the user cannot view his or her photo in Lync 2013, that typically indicates a connectivity problem with Exchange Web Services or with the Exchange autodiscover service.</span></span>

<span data-ttu-id="6f539-133">Notez également qu’aucune configuration supplémentaire n’est requise pour que cette photo soit disponible dans Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6f539-133">Note, too that no additional configuration is required in order to make this photo available in Lync 2013.</span></span> <span data-ttu-id="6f539-134">Au lieu de cela, la photo est immédiatement disponible après avoir été téléchargée et la cmdlet Set-applet userphoto a été exécutée.</span><span class="sxs-lookup"><span data-stu-id="6f539-134">Instead, the photo will be instantly available after it has been uploaded and the Set-UserPhoto cmdlet has been run.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

