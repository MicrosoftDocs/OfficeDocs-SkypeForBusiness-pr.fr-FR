---
title: Mode d’affichage des photos de l’utilisateur dans Lync
description: Mode d’affichage des photos de l’utilisateur dans Lync.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 12ea9e19b3965994c025659f1b2249c49ec32a3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551110"
---
# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="29a0b-103">Mode d’affichage des photos de l’utilisateur dans Lync</span><span class="sxs-lookup"><span data-stu-id="29a0b-103">How user photos are displayed in Lync</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29a0b-104">_**Dernière modification de la rubrique :** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="29a0b-104">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="29a0b-105">**Résumé :** Les photos des utilisateurs affichés dans le client Lync peuvent varier en fonction de la fonctionnalité Lync que vous utilisez, comme dans une conférence ou une conversation par messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="29a0b-105">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="29a0b-106">Lync 2010 a introduit la possibilité d’inclure une photo avec votre profil Lync qui est affiché aux autres utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="29a0b-106">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="29a0b-107">Vous pouvez également choisir d’afficher ou non les photos de vos contacts dans le client Lync.</span><span class="sxs-lookup"><span data-stu-id="29a0b-107">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="29a0b-108">Dans Lync 2013, la prise en charge de photos haute résolution pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="29a0b-108">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="29a0b-109">Cette rubrique explique comment le client Lync obtient et affiche des photos de l’utilisateur, où les images sont stockées, les limites de chaque source d’image et comment les photos des utilisateurs sont utilisées par différents services Lync.</span><span class="sxs-lookup"><span data-stu-id="29a0b-109">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="29a0b-110">Considérations sur la planification</span><span class="sxs-lookup"><span data-stu-id="29a0b-110">Planning considerations</span></span>

<span data-ttu-id="29a0b-111">Vous devez tenir compte des éléments suivants lors de la planification de l’implémentation de la prise en charge des photos des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="29a0b-111">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="29a0b-112">La prise en charge des photos haute définition nécessite que la boîte aux lettres de l’utilisateur se trouve sur Exchange 2013 et le compte d’utilisateur Lync dans le pool Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="29a0b-112">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="29a0b-113">Les photos des utilisateurs de haute définition sont prises en charge uniquement dans un environnement où Lync Server 2013 et Exchange 2013 sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="29a0b-113">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="29a0b-114">Les utilisateurs avec des boîtes aux lettres sur Exchange 2010 utiliseront toujours l’attribut **ThumbNailPhoto** de AD DS comme source de leur photo d’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="29a0b-114">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="29a0b-115">Une photo d’utilisateur stockée en tant qu’attribut **ThumbNailPhoto** à partir d’AD DS ne sera pas affichée aux contacts externes/fédérés.</span><span class="sxs-lookup"><span data-stu-id="29a0b-115">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="29a0b-116">Si les photos des contacts de l’utilisateur sont stockées dans les services de domaine Active Directory, le fichier image utilisé est limité à 96 × 96 pixels et à une taille de fichier de 100 Ko.</span><span class="sxs-lookup"><span data-stu-id="29a0b-116">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="29a0b-117">Si la connectivité entre Lync Server et Exchange Server est perdue, la faible résolution **ThumbNailPhoto** de l’utilisateur à partir d’AD DS sera affichée, et uniquement pour les utilisateurs internes.</span><span class="sxs-lookup"><span data-stu-id="29a0b-117">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="29a0b-118">Les photos des utilisateurs à haute résolution sont affichées dans les réunions Lync 2013 lorsqu’un haut-parleur actif n’est pas activé pour la vidéo.</span><span class="sxs-lookup"><span data-stu-id="29a0b-118">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="29a0b-119">En outre, si vous déplacez la souris sur une photo miniature de la Galerie, la photo haute résolution s’affiche.</span><span class="sxs-lookup"><span data-stu-id="29a0b-119">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="29a0b-120">Photos de l’utilisateur dans Lync 2010</span><span class="sxs-lookup"><span data-stu-id="29a0b-120">User Photos in Lync 2010</span></span>

<span data-ttu-id="29a0b-121">Dans le client Lync 2010, vous avez le choix entre deux options pour afficher la photo de votre profil, l' **image d’entreprise par défaut** et l’affichage **de l’image à partir d’une adresse Web**.</span><span class="sxs-lookup"><span data-stu-id="29a0b-121">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="29a0b-122">Image d’entreprise par défaut</span><span class="sxs-lookup"><span data-stu-id="29a0b-122">Default corporate picture</span></span>

<span data-ttu-id="29a0b-123">Lorsque vous choisissez l’option **d’image d’entreprise par défaut** , Lync obtient la photo affichée pour vous à partir des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="29a0b-123">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="29a0b-124">L’image utilisée est l’image définie comme valeur de l’attribut **ThumbNailPhoto** dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="29a0b-124">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="29a0b-125">Il s’agit du même fichier que celui utilisé par Exchange pour afficher des images dans Outlook.</span><span class="sxs-lookup"><span data-stu-id="29a0b-125">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="29a0b-126">Considérations relatives à l’utilisation d’images à partir des services de domaine Active Directory :</span><span class="sxs-lookup"><span data-stu-id="29a0b-126">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="29a0b-127">Seules les images avec des dimensions jusqu’à 96 pixels par 96 pixels sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="29a0b-127">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="29a0b-128">La taille de fichier de l’image est limitée à 100 Ko.</span><span class="sxs-lookup"><span data-stu-id="29a0b-128">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="29a0b-129">Par défaut, les utilisateurs peuvent modifier l’image utilisée pour l’attribut **ThumbNailPhoto** , mais pas directement via le client Lync.</span><span class="sxs-lookup"><span data-stu-id="29a0b-129">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="29a0b-130">Vous pouvez le désactiver par le biais des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="29a0b-130">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="29a0b-131">Les images stockées dans les services de domaine Active Directory ne sont pas affichées aux contacts externes à votre organisation, même s’il s’agit de contacts fédérés.</span><span class="sxs-lookup"><span data-stu-id="29a0b-131">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="29a0b-132">Dans les grandes organisations, le stockage et l’extraction des images pour un grand nombre d’utilisateurs peuvent avoir un impact sur la taille et les performances de la base de données des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="29a0b-132">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="29a0b-133">Les dimensions limitées de l’image et de la taille des fichiers signifient que seules les images à faible résolution peuvent être utilisées.</span><span class="sxs-lookup"><span data-stu-id="29a0b-133">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="29a0b-134">Comment les utilisateurs gèrent leurs photos utilisateur dans les services de domaine Active Directory</span><span class="sxs-lookup"><span data-stu-id="29a0b-134">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="29a0b-135">L’utilisateur ne peut pas modifier l’image utilisée dans son profil des services de domaine Active Directory directement via le client Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="29a0b-135">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="29a0b-136">Ils peuvent utiliser l’une des options suivantes pour le faire, le cas échéant :</span><span class="sxs-lookup"><span data-stu-id="29a0b-136">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="29a0b-137">**SharePoint Server**     Les utilisateurs peuvent télécharger une photo sur un « mon site » sur un serveur SharePoint, puis [configurer la synchronisation des profils dans SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) pour synchroniser la photo avec l’attribut **ThumbNailPhoto** dans les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="29a0b-137">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="29a0b-138">**Photo stockée sur une URL**     accessible publiquement Les utilisateurs peuvent configurer leur photo utilisateur en spécifiant une URL accessible publiquement pour l’image qu’ils souhaitent utiliser.</span><span class="sxs-lookup"><span data-stu-id="29a0b-138">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="29a0b-139">L’image doit être accessible publiquement sans mot de passe.</span><span class="sxs-lookup"><span data-stu-id="29a0b-139">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="29a0b-140">L’image stockée à l’adresse Web spécifiée est transférée aux autres utilisateurs par le biais de la catégorie de carte de visite dans les informations de présence.</span><span class="sxs-lookup"><span data-stu-id="29a0b-140">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="29a0b-141">Lorsque le client Lync a besoin d’afficher une photo de l’utilisateur, il récupère l’image à partir de l’adresse Web spécifiée.</span><span class="sxs-lookup"><span data-stu-id="29a0b-141">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="29a0b-142">**Applets de commande Exchange 2010 pour Windows PowerShell**     Les administrateurs peuvent exécuter l’applet de commande [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) dans Exchange 2010 Management Shell dans pour gérer l’attribut **ThumbNailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="29a0b-142">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="29a0b-143">Lorsque des images sont importées avec des applets de commande Exchange 2010, la taille du fichier est limitée à 10 Ko.</span><span class="sxs-lookup"><span data-stu-id="29a0b-143">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="29a0b-144">**Outils tiers**     Les utilisateurs peuvent télécharger uniquement leur propre photo vers pour l’attribut **ThumbNailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="29a0b-144">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="29a0b-145">Afficher une image à partir d’une adresse web</span><span class="sxs-lookup"><span data-stu-id="29a0b-145">Show a picture from a web address</span></span>

<span data-ttu-id="29a0b-146">Lorsque vous choisissez l’option **afficher une image à partir d’une adresse Web** , Lync obtient l’image à l’adresse que vous entrez et l’affiche pour votre photo de l’utilisateur dans Lync.</span><span class="sxs-lookup"><span data-stu-id="29a0b-146">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="29a0b-147">Les éléments à prendre en compte pour l’utilisation d’images à partir d’une adresse Web sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="29a0b-147">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="29a0b-148">Les limites de taille de fichier sont déterminées par l’attribut **MaxPhotoSizeKB** dans la stratégie client, définie à l’aide de la cmdlet [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) .</span><span class="sxs-lookup"><span data-stu-id="29a0b-148">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="29a0b-149">La limite de taille par défaut est de 30 Ko.</span><span class="sxs-lookup"><span data-stu-id="29a0b-149">The default size limit is 30 KB.</span></span> <span data-ttu-id="29a0b-150">La valeur maximale est 100 Ko.</span><span class="sxs-lookup"><span data-stu-id="29a0b-150">The maximum value is 100 KB.</span></span> <span data-ttu-id="29a0b-151">Il n’existe aucune restriction quant à la résolution de l’image, mais si vous essayez d’utiliser un fichier image qui dépasse la limite de taille, il ne sera pas téléchargé sur les clients Lync.</span><span class="sxs-lookup"><span data-stu-id="29a0b-151">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="29a0b-152">Vous pouvez définir la valeur sur 0 pour désactiver l’utilisation de toutes les photos des utilisateurs dans Lync.</span><span class="sxs-lookup"><span data-stu-id="29a0b-152">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="29a0b-153">Les photos des utilisateurs d’une adresse Web peuvent être vues par des contacts fédérés externes.</span><span class="sxs-lookup"><span data-stu-id="29a0b-153">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="29a0b-154">Gestion de la photo de l’utilisateur avec des applets de commande de stratégie client</span><span class="sxs-lookup"><span data-stu-id="29a0b-154">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="29a0b-155">Dans Lync Server 2010, les paramètres de stratégie client sont configurés avec les applets de commande CsClientPolicy.</span><span class="sxs-lookup"><span data-stu-id="29a0b-155">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="29a0b-156">Les paramètres de stratégie configurés sont envoyés aux clients via la mise en service intrabande.</span><span class="sxs-lookup"><span data-stu-id="29a0b-156">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="29a0b-157">Les deux paramètres des cmdlets CsClientPolicy qui déterminent l’expérience de photo de l’utilisateur sont **DisplayPhoto** et **MaxPhotoSizeKB**.</span><span class="sxs-lookup"><span data-stu-id="29a0b-157">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="29a0b-158">Le paramètre de mise en service intrabande correspondant pour **DisplayPhoto** et **MaxPhotoSizeKB** est appelé **photousage**.</span><span class="sxs-lookup"><span data-stu-id="29a0b-158">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="29a0b-159">Les valeurs du paramètre de **photoutilisation** sont envoyer aux clients via le **EndpointConfiguration** **provisionGroup**.</span><span class="sxs-lookup"><span data-stu-id="29a0b-159">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="29a0b-160">Pour plus d’informations, voir [Overview of client Policies and Settings](https://go.microsoft.com/fwlink/?linkid=507470) .</span><span class="sxs-lookup"><span data-stu-id="29a0b-160">See [Overview of Client Policies and Settings](https://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="29a0b-161">La valeur du paramètre **DisplayPhoto** détermine la source de l’image photo de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="29a0b-161">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="29a0b-162">Les valeurs prises en charge sont incluses dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="29a0b-162">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29a0b-163">Valeur du paramètre DisplayPhoto</span><span class="sxs-lookup"><span data-stu-id="29a0b-163">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="29a0b-164">Source de l’image</span><span class="sxs-lookup"><span data-stu-id="29a0b-164">Image source</span></span></th>
<th><span data-ttu-id="29a0b-165">Paramètres du client Lync 2010</span><span class="sxs-lookup"><span data-stu-id="29a0b-165">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29a0b-166">NoPhoto</span><span class="sxs-lookup"><span data-stu-id="29a0b-166">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="29a0b-167">aucune</span><span class="sxs-lookup"><span data-stu-id="29a0b-167">none</span></span></p></td>
<td><p><span data-ttu-id="29a0b-168"><strong>Ne pas afficher mon image</strong></span><span class="sxs-lookup"><span data-stu-id="29a0b-168"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29a0b-169">PhotoFromADOnly</span><span class="sxs-lookup"><span data-stu-id="29a0b-169">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="29a0b-170">Active Directory</span><span class="sxs-lookup"><span data-stu-id="29a0b-170">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="29a0b-171"><strong>Image d’entreprise par défaut</strong></span><span class="sxs-lookup"><span data-stu-id="29a0b-171"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29a0b-172">AllPhotos</span><span class="sxs-lookup"><span data-stu-id="29a0b-172">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="29a0b-173">Adresse Web</span><span class="sxs-lookup"><span data-stu-id="29a0b-173">Web address</span></span></p></td>
<td><p><span data-ttu-id="29a0b-174"><strong>Afficher une image à partir d’une adresse web</strong></span><span class="sxs-lookup"><span data-stu-id="29a0b-174"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="29a0b-175">Comment Lync 2010 client obtient des photos</span><span class="sxs-lookup"><span data-stu-id="29a0b-175">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="29a0b-176">Dans Lync 2010, les photos des utilisateurs sont gérées sur le serveur par le service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="29a0b-176">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="29a0b-177">Le client Lync obtient des photos de l’utilisateur en interrogeant d’abord le service de requête Web de carnet d’adresses (ABWQ) sur le serveur, qui est exposé via le service Web de développement de liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="29a0b-177">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="29a0b-178">Le client reçoit le fichier image, puis le copie dans le cache de l’utilisateur pour éviter de télécharger l’image à chaque fois qu’il doit être affiché.</span><span class="sxs-lookup"><span data-stu-id="29a0b-178">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="29a0b-179">Les valeurs d’attribut renvoyées par la requête sont également stockées dans l’entrée du service de carnet d’adresses mis en cache pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="29a0b-179">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="29a0b-180">Le service de carnet d’adresses supprime toutes les images mises en cache toutes les 24 heures, ce qui signifie qu’il peut mettre jusqu’à 24 heures pour que les nouvelles images utilisateur soient mises à jour dans le cache du serveur.</span><span class="sxs-lookup"><span data-stu-id="29a0b-180">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="29a0b-181">Vous pouvez forcer une mise à jour du cache à l’aide de la cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .</span><span class="sxs-lookup"><span data-stu-id="29a0b-181">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="29a0b-182">Les photos des utilisateurs incluses dans le statut de présence ont également une valeur de hachage associée que le client Lync utilise pour déterminer s’il existe une image plus récente disponible.</span><span class="sxs-lookup"><span data-stu-id="29a0b-182">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="29a0b-183">Le client est automatiquement informé des modifications apportées au fichier image utilisé dans l’état de présence.</span><span class="sxs-lookup"><span data-stu-id="29a0b-183">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="29a0b-184">Étant donné que les photos ne sont pas stockées dans la base de données GalContacts. DB, le téléchargement des photos des utilisateurs n’est pas dépendant du paramètre <STRONG>AddressBookAvailability</STRONG> dans la stratégie client (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span><span class="sxs-lookup"><span data-stu-id="29a0b-184">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="29a0b-185">La requête au service ABWQ inclut les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="29a0b-185">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="29a0b-186">**Photohash**     La valeur de hachage des données de la photo binaire et est utilisée pour déterminer si la photo active a été modifiée.</span><span class="sxs-lookup"><span data-stu-id="29a0b-186">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="29a0b-187">**PhotoRelPath**     Chemin d’accès relatif au fichier image stocké sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="29a0b-187">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="29a0b-188">**Photodimensionnement**     Taille du fichier image, en octets.</span><span class="sxs-lookup"><span data-stu-id="29a0b-188">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="29a0b-189">**Timestamp**     Date et heure du dernier téléchargement du fichier image à partir du serveur et copié dans le cache client.</span><span class="sxs-lookup"><span data-stu-id="29a0b-189">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="29a0b-190">Ensuite, après avoir extrait le fichier image, le client Lync 2010 compare les valeurs d’attribut retournées par la requête aux valeurs d’attribut reçues par le client à partir de la mise en service intrabande afin de déterminer si elles sont différentes.</span><span class="sxs-lookup"><span data-stu-id="29a0b-190">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="29a0b-191">Si les valeurs sont différentes, le client récupère le fichier image de l’utilisateur connecté à l’aide d’une demande HTTP GET.</span><span class="sxs-lookup"><span data-stu-id="29a0b-191">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="29a0b-192">En outre, le client vérifie avec le serveur toutes les 24 heures après l’heure à laquelle la version mise en cache du fichier image a été créée pour comparer la valeur de l’attribut de **photohachage** sur le serveur avec la valeur sur le client.</span><span class="sxs-lookup"><span data-stu-id="29a0b-192">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="29a0b-193">Si les valeurs sont différentes, le client sait que le fichier image a été modifié.</span><span class="sxs-lookup"><span data-stu-id="29a0b-193">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="29a0b-194">Pour obtenir le fichier image mis à jour, le client interroge à nouveau le service ABWQ afin de mettre à jour le fichier image dans le cache client avec le fichier image sur le serveur, ce qui réinitialise également l' **horodatage** du fichier dans le cache client.</span><span class="sxs-lookup"><span data-stu-id="29a0b-194">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="29a0b-195">Voici un exemple de réponse à une requête vers le service ABWQ :</span><span class="sxs-lookup"><span data-stu-id="29a0b-195">The following is an example response to a query to the ABWQ service:</span></span>
```xml
    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="29a0b-196">Photos de l’utilisateur dans Lync 2013</span><span class="sxs-lookup"><span data-stu-id="29a0b-196">User photos in Lync 2013</span></span>

<span data-ttu-id="29a0b-197">Lync 2013 a introduit une prise en charge pour les images haute résolution pour les photos des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="29a0b-197">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="29a0b-198">Lync 2013 prend également en charge le stockage des photos des utilisateurs dans la boîte aux lettres de l’utilisateur sur Exchange 2013, ce qui supprime la résolution d’image et les limitations de taille présentes dans Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="29a0b-198">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="29a0b-199">Les photos des utilisateurs dans Lync 2013 peuvent atteindre 648 pixels par 648 pixels avec une taille de fichier maximale de 20 Mo.</span><span class="sxs-lookup"><span data-stu-id="29a0b-199">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="29a0b-200">Les photos haute résolution dans Lync 2013 doivent se trouver dans la boîte aux lettres de l’utilisateur sur Exchange 2013 et sont prises en charge uniquement avec le client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="29a0b-200">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="29a0b-201">Cette intégration avec Exchange tire parti de la nouvelle infrastructure d’autorisation incluse dans les versions 2013 de Lync, Exchange et SharePoint, appelée OAuth.</span><span class="sxs-lookup"><span data-stu-id="29a0b-201">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="29a0b-202">Si Exchange 2013 n’est pas utilisé dans votre déploiement, la prise en charge des photos des utilisateurs est identique à celle de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="29a0b-202">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="29a0b-203">Toutefois, les options utilisateur permettant de choisir la photo à utiliser sont différentes dans Lync 2013 client.</span><span class="sxs-lookup"><span data-stu-id="29a0b-203">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="29a0b-204">Dans le client Lync 2013, les utilisateurs peuvent sélectionner **Masquer mon image** ou **afficher mon image**.</span><span class="sxs-lookup"><span data-stu-id="29a0b-204">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="29a0b-205">L’option **afficher une image d’un site Web** n’est pas disponible par défaut, mais peut être activée en affectant une stratégie client.</span><span class="sxs-lookup"><span data-stu-id="29a0b-205">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="29a0b-206">Masquer mon image</span><span class="sxs-lookup"><span data-stu-id="29a0b-206">Hide my picture</span></span>

<span data-ttu-id="29a0b-207">Les paramètres pour les photos des utilisateurs figurent dans la boîte de dialogue **options** de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="29a0b-207">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="29a0b-208">Lorsque vous sélectionnez **Masquer mon image**, aucune photo de l’utilisateur n’est affichée dans le client Lync, mais votre photo est toujours affichée sur la carte de visite et en dehors de Lync.</span><span class="sxs-lookup"><span data-stu-id="29a0b-208">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="29a0b-209">Afficher mon image</span><span class="sxs-lookup"><span data-stu-id="29a0b-209">Show my picture</span></span>

<span data-ttu-id="29a0b-210">Lorsque vous choisissez l’option **afficher mon image** , votre photo de l’utilisateur s’affiche dans votre client Lync et aux autres utilisateurs dans les conversations Lync.</span><span class="sxs-lookup"><span data-stu-id="29a0b-210">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="29a0b-211">L’image utilisée est celle stockée dans les services de domaine Active Directory (AD DS).</span><span class="sxs-lookup"><span data-stu-id="29a0b-211">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="29a0b-212">Afficher une image à partir d’un site Web</span><span class="sxs-lookup"><span data-stu-id="29a0b-212">Show a picture from a website</span></span>

<span data-ttu-id="29a0b-213">L’option **afficher l’image d’un site Web** devient disponible dans Lync 2013 une fois qu’une stratégie client est configurée pour l’activer.</span><span class="sxs-lookup"><span data-stu-id="29a0b-213">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="29a0b-214">La version du client doit être plus récente que 15.0.4535.1002, qui est installée avec les [mises à jour cumulatives Lync : novembre 2013](https://go.microsoft.com/fwlink/p/?linkid=509908).</span><span class="sxs-lookup"><span data-stu-id="29a0b-214">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](https://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="29a0b-215">Il se peut que les utilisateurs doivent se déconnecter puis se reconnecter pour voir les modifications apportées au client.</span><span class="sxs-lookup"><span data-stu-id="29a0b-215">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="29a0b-216">Vous pouvez définir la stratégie client pour activer l' **affichage des images à partir d’un paramètre de site Web** en exécutant la stratégie [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) dans Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="29a0b-216">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="29a0b-217">Les exemples de cmdlets suivants montrent comment définir la stratégie globalement pour tous les utilisateurs de votre déploiement :</span><span class="sxs-lookup"><span data-stu-id="29a0b-217">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


<span data-ttu-id="29a0b-218">Lorsqu’une image est chargée dans la boîte aux lettres de l’utilisateur, Exchange crée automatiquement une version moins élevée de l’image qui peut être utilisée dans les applications clientes.</span><span class="sxs-lookup"><span data-stu-id="29a0b-218">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="29a0b-219">La photo de l’utilisateur est également mise à jour dans AD DS.</span><span class="sxs-lookup"><span data-stu-id="29a0b-219">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="29a0b-220">Lorsqu’un fichier image est mis à jour dans AD DS, une image 48 x 48 pixel est créée et utilisée pour le thumbnailPhoto dans AD DS.</span><span class="sxs-lookup"><span data-stu-id="29a0b-220">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="29a0b-221">Toutes les images existantes sont remplacées.</span><span class="sxs-lookup"><span data-stu-id="29a0b-221">Any existing image is replaced.</span></span> <span data-ttu-id="29a0b-222">Par conséquent, si vous avez ajouté une image 96 x 96 à AD DS, celle-ci sera remplacée par la nouvelle image 48 x 48.</span><span class="sxs-lookup"><span data-stu-id="29a0b-222">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="29a0b-223">Cette opération n’est importante que si vous avez des utilisateurs dans votre environnement utilisant des clients Lync 2010, car ces clients obtiendront des photos de l’utilisateur dans AD DS.</span><span class="sxs-lookup"><span data-stu-id="29a0b-223">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="29a0b-224">Vous pouvez importer des images 96 x 96 pixels pour remplacer celles créées par AD DS si vous avez des clients Lync 2010 dans votre organisation.</span><span class="sxs-lookup"><span data-stu-id="29a0b-224">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="29a0b-225">Prise en charge des photos de l’utilisateur dans Lync 2013</span><span class="sxs-lookup"><span data-stu-id="29a0b-225">User photo support in Lync 2013</span></span>

<span data-ttu-id="29a0b-226">Dans Lync 2013, trois résolutions d’image sont prises en charge pour les photos des utilisateurs, comme décrit dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="29a0b-226">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="29a0b-227">L’image utilisée est déterminée par le paramètre de stratégie client attribué aux utilisateurs Lync.</span><span class="sxs-lookup"><span data-stu-id="29a0b-227">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="29a0b-228">Pour plus d’informations, consultez la rubrique sur la gestion de la photo de l’utilisateur avec des applets de commande de stratégie client.</span><span class="sxs-lookup"><span data-stu-id="29a0b-228">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29a0b-229">Résolution de l’image (pixels)</span><span class="sxs-lookup"><span data-stu-id="29a0b-229">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="29a0b-230">Application</span><span class="sxs-lookup"><span data-stu-id="29a0b-230">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29a0b-231">48 x 48</span><span class="sxs-lookup"><span data-stu-id="29a0b-231">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="29a0b-232">Utilisé si aucune image de résolution supérieure n’est sélectionnée</span><span class="sxs-lookup"><span data-stu-id="29a0b-232">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29a0b-233">96 x 96</span><span class="sxs-lookup"><span data-stu-id="29a0b-233">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="29a0b-234">Utilisé dans Outlook Web App et Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="29a0b-234">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29a0b-235">648 x 648</span><span class="sxs-lookup"><span data-stu-id="29a0b-235">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="29a0b-236">Utilisé dans le client de bureau Lync 2013 et dans Lync 2013 Web App</span><span class="sxs-lookup"><span data-stu-id="29a0b-236">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="29a0b-237">Tout utilisateur disposant d’une boîte aux lettres activée dans Exchange 2013 peut télécharger une autre image, y compris des photos haute résolution, via les options du client Outlook Web Access ou Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="29a0b-237">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="29a0b-238">Les paramètres recommandés pour les images utilisées sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="29a0b-238">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="29a0b-239">Résolution de l' **image**     648 par 648 pixels</span><span class="sxs-lookup"><span data-stu-id="29a0b-239">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="29a0b-240">**Profondeur**     de couleur 24 bits</span><span class="sxs-lookup"><span data-stu-id="29a0b-240">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="29a0b-241">Taille du fichier **image**     jusqu’à 20 Mo</span><span class="sxs-lookup"><span data-stu-id="29a0b-241">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="29a0b-242">**Format**     de fichier FORMAT</span><span class="sxs-lookup"><span data-stu-id="29a0b-242">**File format**   JPEG</span></span>

<span data-ttu-id="29a0b-243">Une image JPEG standard de 24 bits 648 pixels par 648 pixels a une taille d’environ 240 Ko, de sorte que 1 Mo d’espace de stockage est nécessaire pour 4 photos utilisateur.</span><span class="sxs-lookup"><span data-stu-id="29a0b-243">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

