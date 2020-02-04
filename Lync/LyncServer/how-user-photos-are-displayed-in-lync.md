---
title: Comment les photos d’utilisateur sont affichées dans Lync
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8cd3214c3ada87db6f44f6b99373346d4f0a27d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730694"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a><span data-ttu-id="ff784-102">Comment les photos d’utilisateur sont affichées dans Lync</span><span class="sxs-lookup"><span data-stu-id="ff784-102">How user photos are displayed in Lync</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff784-103">_**Dernière modification de la rubrique :** 2014-08-25_</span><span class="sxs-lookup"><span data-stu-id="ff784-103">_**Topic Last Modified:** 2014-08-25_</span></span>

<span data-ttu-id="ff784-104">**Résumé :** Les photos des utilisateurs affichées dans le client Lync peuvent être différentes selon la fonctionnalité Lync que vous utilisez, par exemple, lors d’une conférence téléphonique ou d’une conversation par messagerie instantanée.</span><span class="sxs-lookup"><span data-stu-id="ff784-104">**Summary:** User photos displayed in Lync client can be different depending on which Lync feature you are using, such as when in a conference or an IM chat.</span></span>

<span data-ttu-id="ff784-105">Lync 2010 a introduit la possibilité d’inclure une photo avec votre profil Lync qui s’affiche pour les autres utilisateurs Lync.</span><span class="sxs-lookup"><span data-stu-id="ff784-105">Lync 2010 introduced the ability to include a photo with your Lync profile that is displayed to other Lync users.</span></span> <span data-ttu-id="ff784-106">Vous pouvez également choisir d’afficher ou non les photos de vos contacts dans le client Lync.</span><span class="sxs-lookup"><span data-stu-id="ff784-106">You can also choose whether or not to display photos for your contacts in Lync client.</span></span> <span data-ttu-id="ff784-107">Dans Lync 2013, prise en charge de photos haute résolution pour les utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ff784-107">In Lync 2013, support for high-resolution photos for users.</span></span> <span data-ttu-id="ff784-108">Cette rubrique décrit la façon dont le client Lync obtient et affiche les photos des utilisateurs, l’emplacement de stockage des images, les limitations pour chaque source d’image et la façon dont les photos des utilisateurs sont utilisées par différents services Lync.</span><span class="sxs-lookup"><span data-stu-id="ff784-108">This topic describes how Lync client gets and displays user photos, where the images are stored, the limitations for each image source, and how user photos are used by different Lync services.</span></span>

<div>

## <a name="planning-considerations"></a><span data-ttu-id="ff784-109">Considérations en matière de planification</span><span class="sxs-lookup"><span data-stu-id="ff784-109">Planning considerations</span></span>

<span data-ttu-id="ff784-110">Prenez en considération les points suivants lors de la planification de la prise en charge des photos des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ff784-110">You should consider the following when planning to implement support for user photos.</span></span>

  - <span data-ttu-id="ff784-111">La prise en charge des photos haute définition nécessite que la boîte aux lettres de l’utilisateur soit située sur Exchange 2013 et le compte d’utilisateur Lync dans le pool 2013.</span><span class="sxs-lookup"><span data-stu-id="ff784-111">High-definition user photo support requires that the user’s mailbox be located on Exchange 2013 and the Lync user account to be in Lync 2013 pool.</span></span>

  - <span data-ttu-id="ff784-112">Les photos des utilisateurs haute définition sont uniquement prises en charge dans un environnement dans lequel Lync Server 2013 et Exchange 2013 sont utilisés.</span><span class="sxs-lookup"><span data-stu-id="ff784-112">High-definition user photos are supported only in an environment where both Lync Server 2013 and Exchange 2013 are used.</span></span>

  - <span data-ttu-id="ff784-113">Les utilisateurs dotés d’une boîte aux lettres sur Exchange 2010 utilisent toujours l’attribut **ThumbNailPhoto** d’AD DS comme source de la photo de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ff784-113">Users with Mailboxes on Exchange 2010 will always use the **thumbnailPhoto** attribute from AD DS as the source for their user photo.</span></span>

  - <span data-ttu-id="ff784-114">Une photo de l’utilisateur stockée en tant qu’attribut **ThumbNailPhoto** d’AD DS ne sera pas affichée pour les contacts externes/fédérés.</span><span class="sxs-lookup"><span data-stu-id="ff784-114">A user photo stored as the **thumbnailPhoto** attribute from AD DS will not be displayed to external / federated contacts.</span></span>

  - <span data-ttu-id="ff784-115">Si les photos des contacts de l’utilisateur sont stockées dans AD DS, le fichier image utilisé est limité à 96 x 96 pixels et ne dépasse pas la taille du fichier de 100 Ko.</span><span class="sxs-lookup"><span data-stu-id="ff784-115">If the photos for user contacts are stored in AD DS, the image file used is limited to 96×96 pixels and no more than 100 KB file size.</span></span>

  - <span data-ttu-id="ff784-116">Si la connectivité entre Lync Server et Exchange Server est perdue, le **ThumbNailPhoto** de la résolution basse de l’utilisateur à partir d’AD DS est affiché et ne peut être affiché qu’aux utilisateurs internes.</span><span class="sxs-lookup"><span data-stu-id="ff784-116">If connectivity between Lync Server and Exchange Server is lost, the user’s low resolution **thumbnailPhoto** from AD DS will be displayed, and to internal users only.</span></span>

  - <span data-ttu-id="ff784-117">Les photos des utilisateurs haute résolution sont affichées dans les réunions 2013 Lync lorsque la vidéo n’est pas activée pour le haut-parleur actif.</span><span class="sxs-lookup"><span data-stu-id="ff784-117">High-resolution user photos are displayed in Lync 2013 meetings when an active speaker does not have video enabled.</span></span> <span data-ttu-id="ff784-118">Par ailleurs, le déplacement de la souris sur la photo miniature dans la Galerie affiche la photo haute résolution.</span><span class="sxs-lookup"><span data-stu-id="ff784-118">Also, moving the mouse over thumbnail photo in the gallery will display the high-resolution photo.</span></span>

</div>

<div>

## <a name="user-photos-in-lync-2010"></a><span data-ttu-id="ff784-119">Photos des utilisateurs dans Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ff784-119">User Photos in Lync 2010</span></span>

<span data-ttu-id="ff784-120">Dans le client Lync 2010, vous avez le choix entre deux options pour afficher une photo de votre profil, une **image d’entreprise par défaut** et **afficher une image à partir d’une adresse Web**.</span><span class="sxs-lookup"><span data-stu-id="ff784-120">In the Lync 2010 client, you can choose from two options to display a photo for your profile, **Default corporate picture** and **Show picture from a web address**.</span></span>

<div>

## <a name="default-corporate-picture"></a><span data-ttu-id="ff784-121">Image d’entreprise par défaut</span><span class="sxs-lookup"><span data-stu-id="ff784-121">Default corporate picture</span></span>

<span data-ttu-id="ff784-122">Lorsque vous choisissez l’option **d’image d’entreprise par défaut** , Lync obtient la photo qui vous est affichée dans les services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="ff784-122">When you choose the **Default corporate picture** option, Lync gets the photo displayed for you from Active Directory Domain Services.</span></span> <span data-ttu-id="ff784-123">L’image utilisée est l’image définie en tant que valeur de l’attribut **ThumbNailPhoto** dans les services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="ff784-123">The image used is the image defined as the value for the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span> <span data-ttu-id="ff784-124">Il s’agit du fichier utilisé par Exchange pour afficher des images dans Outlook.</span><span class="sxs-lookup"><span data-stu-id="ff784-124">This is the same file that is used by Exchange to display images in Outlook.</span></span>

<span data-ttu-id="ff784-125">Voici quelques éléments à prendre en compte lors de l’utilisation d’images provenant des services de domaine Active Directory :</span><span class="sxs-lookup"><span data-stu-id="ff784-125">Considerations for using images from Active Directory Domain Services include the following:</span></span>

  - <span data-ttu-id="ff784-126">Seules les images dont la taille ne doit pas être de 96 96 pixels sont prises en charge.</span><span class="sxs-lookup"><span data-stu-id="ff784-126">Only images with dimensions up to 96 pixels by 96 pixels are supported.</span></span> <span data-ttu-id="ff784-127">La taille de fichier de l’image est limitée à 100 Ko.</span><span class="sxs-lookup"><span data-stu-id="ff784-127">The file size for the image is limited to 100 KB.</span></span>

  - <span data-ttu-id="ff784-128">Par défaut, les utilisateurs peuvent modifier l’image utilisée pour l’attribut **ThumbNailPhoto** , mais pas directement via le client Lync.</span><span class="sxs-lookup"><span data-stu-id="ff784-128">By default, users are able to change the image used for the **thumbnailPhoto** attribute, though not directly through Lync client.</span></span> <span data-ttu-id="ff784-129">Vous pouvez désactiver ce service via les services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ff784-129">You can disable this through Active Directory Domain Services.</span></span>

  - <span data-ttu-id="ff784-130">Les images stockées dans les services de domaine Active Directory ne s’affichent pas pour les contacts externes à votre organisation, même s’ils sont des contacts fédérés.</span><span class="sxs-lookup"><span data-stu-id="ff784-130">Images stored in Active Directory Domain Services are not displayed to contacts external to your organization, even if they are federated contacts.</span></span>

  - <span data-ttu-id="ff784-131">Dans de grandes organisations, le stockage et la récupération des images pour de nombreux utilisateurs peuvent avoir un impact sur les performances et la taille de la base de données des services de domaine Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ff784-131">In large organizations, storing and retrieving the images for large numbers of users may impact the Active Directory Domain Services database size and performance.</span></span>

  - <span data-ttu-id="ff784-132">La taille de fichier et les dimensions d’image limitées indiquent que seules les images de faible résolution peuvent être utilisées.</span><span class="sxs-lookup"><span data-stu-id="ff784-132">The limited image dimensions and file size mean that only low resolution images can be used.</span></span>

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a><span data-ttu-id="ff784-133">Comment les utilisateurs gèrent leurs photos utilisateur dans les services de domaine Active Directory (AD FS)</span><span class="sxs-lookup"><span data-stu-id="ff784-133">How users manage their user photos in Active Directory Domain Services</span></span>

<span data-ttu-id="ff784-134">L’utilisateur ne peut pas modifier l’image utilisée dans son profil de services de domaine Active Directory directement via le client Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="ff784-134">User cannot change the image used in their Active Directory Domain Services profile directly through Lync 2010 client.</span></span> <span data-ttu-id="ff784-135">Pour cela, vous pouvez utiliser l’une des options suivantes, le cas échéant :</span><span class="sxs-lookup"><span data-stu-id="ff784-135">They can use one of the following options to do so, if available:</span></span>

  - <span data-ttu-id="ff784-136">\*\*\*\*   Les utilisateurs de SharePoint Server peuvent télécharger une photo sur’mon site’sur un serveur SharePoint, puis [configurer la synchronisation des profils dans SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) pour synchroniser la photo avec l’attribut **ThumbNailPhoto** dans les services de domaine Active Directory (AD FS).</span><span class="sxs-lookup"><span data-stu-id="ff784-136">**SharePoint Server**   Users can upload a photo to ‘My Site’ on a SharePoint Server and then [configure profile synchronization in SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) to synchronize the photo to the **thumbnailPhoto** attribute in Active Directory Domain Services.</span></span>

  - <span data-ttu-id="ff784-137">**Photo stockée sur des URL**   accessibles publiquement les utilisateurs peuvent configurer leur photo utilisateur en spécifiant une URL accessible publiquement pour l’image qu’ils souhaitent utiliser.</span><span class="sxs-lookup"><span data-stu-id="ff784-137">**Photo stored on publicly accessible URL**   Users can configure their user photo specifying a publicly accessible URL for the image that they want to use.</span></span> <span data-ttu-id="ff784-138">L’image doit être accessible au public sans mot de passe.</span><span class="sxs-lookup"><span data-stu-id="ff784-138">The image must be publicly accessible without a password.</span></span> <span data-ttu-id="ff784-139">L’image stockée à l’adresse Web spécifiée est transférée à d’autres utilisateurs via la catégorie carte de contact des informations de présence.</span><span class="sxs-lookup"><span data-stu-id="ff784-139">The image stored at the specified web address is transferred to other users through the contact card category in the presence information.</span></span> <span data-ttu-id="ff784-140">Lorsque le client Lync doit afficher une photo de l’utilisateur, il récupère l’image à partir de l’adresse Web spécifiée.</span><span class="sxs-lookup"><span data-stu-id="ff784-140">When Lync client needs to display a user photo, it retrieves the image from the specified web address.</span></span>

  - <span data-ttu-id="ff784-141">**Les applets de RecipientDataProperty 2010 Exchange pour les administrateurs Windows PowerShell**   peuvent exécuter l’applet de passe [Import-](http://go.microsoft.com/fwlink/p/?linkid=507468) dans Exchange 2010 Management Shell pour gérer l’attribut **ThumbNailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="ff784-141">**Exchange 2010 cmdlets for Windows PowerShell**   Administrators can run the [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) cmdlet in the Exchange 2010 Management Shell in to manage the **thumbnailPhoto** attribute.</span></span> <span data-ttu-id="ff784-142">Lorsque les images sont importées à l’aide des applets de applet de passe Exchange 2010, la taille du fichier est limitée à 10 Ko.</span><span class="sxs-lookup"><span data-stu-id="ff784-142">When images are imported with Exchange 2010 cmdlets, the file size is limited to 10 KB.</span></span>

  - <span data-ttu-id="ff784-143">**Outils tiers les**   utilisateurs peuvent télécharger uniquement leur propre photo vers pour l’attribut **ThumbNailPhoto** .</span><span class="sxs-lookup"><span data-stu-id="ff784-143">**Third Party tools**   Users can upload only their own photo to for the **thumbnailPhoto** attribute.</span></span>

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a><span data-ttu-id="ff784-144">Afficher une image à partir d’une adresse Web</span><span class="sxs-lookup"><span data-stu-id="ff784-144">Show a picture from a web address</span></span>

<span data-ttu-id="ff784-145">Lorsque vous choisissez l’option **afficher une image à partir d’une adresse Web** , Lync obtient l’image à l’adresse que vous entrez et l’affiche pour votre photo de l’utilisateur dans Lync.</span><span class="sxs-lookup"><span data-stu-id="ff784-145">When you choose the **Show a picture from a web address** option, Lync gets the image at the address you enter and displays it for your user photo in Lync.</span></span>

<span data-ttu-id="ff784-146">Voici quelques éléments à prendre en compte lors de l’utilisation d’images issues d’une adresse Web :</span><span class="sxs-lookup"><span data-stu-id="ff784-146">Considerations for using images from a web address include the following:</span></span>

  - <span data-ttu-id="ff784-147">Les limites de taille de fichier sont déterminées par l’attribut **MaxPhotoSizeKB** dans la stratégie client, définie à l’aide de l’applet [de nouvelle cmdlet New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) .</span><span class="sxs-lookup"><span data-stu-id="ff784-147">File size limits are determined by the **MaxPhotoSizeKB** attribute in the client policy, defined with the [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) cmdlet.</span></span> <span data-ttu-id="ff784-148">La taille limite par défaut est de 30 Ko.</span><span class="sxs-lookup"><span data-stu-id="ff784-148">The default size limit is 30 KB.</span></span> <span data-ttu-id="ff784-149">La valeur maximale est 100 Ko.</span><span class="sxs-lookup"><span data-stu-id="ff784-149">The maximum value is 100 KB.</span></span> <span data-ttu-id="ff784-150">Il n’existe aucune restriction sur la résolution de l’image, mais si vous essayez d’utiliser un fichier image dont la taille est supérieure à la limite de taille, elle ne sera pas téléchargée vers les clients Lync.</span><span class="sxs-lookup"><span data-stu-id="ff784-150">There is no restriction on the resolution of the image, but if you try to use an image file that exceeds the size limit it will not be downloaded to Lync clients.</span></span> <span data-ttu-id="ff784-151">Vous pouvez définir la valeur sur 0 pour désactiver l’utilisation de toutes les photos des utilisateurs dans Lync.</span><span class="sxs-lookup"><span data-stu-id="ff784-151">You can set the value to 0 to disable all user photos from being used in Lync.</span></span>

  - <span data-ttu-id="ff784-152">Les photos des utilisateurs d’une adresse Web peuvent être consultées par des contacts fédérés externes.</span><span class="sxs-lookup"><span data-stu-id="ff784-152">User photos from a web address can be seen by external federated contacts.</span></span>

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a><span data-ttu-id="ff784-153">Gestion de la photo de l’utilisateur à l’aide des cmdlets de stratégie client</span><span class="sxs-lookup"><span data-stu-id="ff784-153">Managing user’s photo with Client Policy cmdlets</span></span>

<span data-ttu-id="ff784-154">Dans Lync Server 2010, les paramètres de stratégie de client sont configurés avec les applets de fonction CsClientPolicy.</span><span class="sxs-lookup"><span data-stu-id="ff784-154">In Lync Server 2010, client policy settings are configured with the CsClientPolicy cmdlets.</span></span> <span data-ttu-id="ff784-155">Les paramètres de stratégie configurés sont envoyés aux clients par le biais de la mise en service intrabande.</span><span class="sxs-lookup"><span data-stu-id="ff784-155">The configured policy settings are sent to clients through in-band provisioning.</span></span> <span data-ttu-id="ff784-156">Les deux paramètres des cmdlets CsClientPolicy qui déterminent l’utilisation de la photo de l’utilisateur sont **DisplayPhoto** et **MaxPhotoSizeKB**.</span><span class="sxs-lookup"><span data-stu-id="ff784-156">The two parameters of the CsClientPolicy cmdlets that determine the user photo experience are **DisplayPhoto** and **MaxPhotoSizeKB**.</span></span> <span data-ttu-id="ff784-157">Le paramètre de mise en service intrabande correspondant pour **DisplayPhoto** et **MaxPhotoSizeKB** est appelé **photousage**.</span><span class="sxs-lookup"><span data-stu-id="ff784-157">The corresponding in-band provisioning parameter for **DisplayPhoto** and **MaxPhotoSizeKB** is named **PhotoUsage**.</span></span> <span data-ttu-id="ff784-158">Les valeurs du paramètre **photousage** sont envoyées aux clients via le **EndpointConfiguration** **provisionGroup**.</span><span class="sxs-lookup"><span data-stu-id="ff784-158">Values for the **PhotoUsage** parameter are send to clients through the **endpointConfiguration** **provisionGroup**.</span></span> <span data-ttu-id="ff784-159">Pour plus d’informations, voir [vue d’ensemble des stratégies et des paramètres du client](http://go.microsoft.com/fwlink/?linkid=507470) .</span><span class="sxs-lookup"><span data-stu-id="ff784-159">See [Overview of Client Policies and Settings](http://go.microsoft.com/fwlink/?linkid=507470) for more information.</span></span>

<span data-ttu-id="ff784-160">La valeur du paramètre **DisplayPhoto** détermine la source de l’image photo de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ff784-160">The **DisplayPhoto** parameter value determines the source of the user's photo image.</span></span> <span data-ttu-id="ff784-161">Les valeurs prises en charge sont indiquées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="ff784-161">The supported values are included in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff784-162">Valeur du paramètre DisplayPhoto</span><span class="sxs-lookup"><span data-stu-id="ff784-162">DisplayPhoto parameter value</span></span></th>
<th><span data-ttu-id="ff784-163">Source d’image</span><span class="sxs-lookup"><span data-stu-id="ff784-163">Image source</span></span></th>
<th><span data-ttu-id="ff784-164">Paramètres du client Lync 2010</span><span class="sxs-lookup"><span data-stu-id="ff784-164">Lync 2010 client settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff784-165">NoPhoto</span><span class="sxs-lookup"><span data-stu-id="ff784-165">NoPhoto</span></span></p></td>
<td><p><span data-ttu-id="ff784-166">néant</span><span class="sxs-lookup"><span data-stu-id="ff784-166">none</span></span></p></td>
<td><p><span data-ttu-id="ff784-167"><strong>Ne pas afficher mon image</strong></span><span class="sxs-lookup"><span data-stu-id="ff784-167"><strong>Do not show my picture</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff784-168">PhotoFromADOnly</span><span class="sxs-lookup"><span data-stu-id="ff784-168">PhotoFromADOnly</span></span></p></td>
<td><p><span data-ttu-id="ff784-169">Active Directory</span><span class="sxs-lookup"><span data-stu-id="ff784-169">Active Directory</span></span></p></td>
<td><p><span data-ttu-id="ff784-170"><strong>Image d’entreprise par défaut</strong></span><span class="sxs-lookup"><span data-stu-id="ff784-170"><strong>Default corporate picture</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff784-171">AllPhotos</span><span class="sxs-lookup"><span data-stu-id="ff784-171">AllPhotos</span></span></p></td>
<td><p><span data-ttu-id="ff784-172">Adresse Web</span><span class="sxs-lookup"><span data-stu-id="ff784-172">Web address</span></span></p></td>
<td><p><span data-ttu-id="ff784-173"><strong>Afficher une image à partir d’une adresse Web</strong></span><span class="sxs-lookup"><span data-stu-id="ff784-173"><strong>Show a picture from a web address</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a><span data-ttu-id="ff784-174">Comment le client 2010 Lync obtient des photos</span><span class="sxs-lookup"><span data-stu-id="ff784-174">How Lync 2010 client gets photos</span></span>

<span data-ttu-id="ff784-175">Dans Lync 2010, les photos des utilisateurs sont gérées sur le serveur par le service de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="ff784-175">In Lync 2010, user photos are managed on the server by the Address Book Service.</span></span> <span data-ttu-id="ff784-176">Le client Lync obtient les photos des utilisateurs en interrogeant d’abord le service de requête sur le carnet d’adresses (ABWQ) sur le serveur, présenté par le biais du service Web d’extension de liste de distribution.</span><span class="sxs-lookup"><span data-stu-id="ff784-176">Lync client gets user photos by first querying the Address Book Web Query (ABWQ) service on the server, which is exposed through the Distribution List Expansion web service.</span></span> <span data-ttu-id="ff784-177">Le client reçoit le fichier image, puis le copie dans le cache de l’utilisateur pour éviter de télécharger l’image chaque fois qu’il doit être affiché.</span><span class="sxs-lookup"><span data-stu-id="ff784-177">The client receives the image file and then copies it to the user's cache to avoid downloading the image each time it needs to be displayed.</span></span> <span data-ttu-id="ff784-178">Les valeurs d’attribut renvoyées par la requête sont également stockées dans l’entrée du service de carnet d’adresses mise en cache pour l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ff784-178">The attribute values returned from the query are also stored in the cached Address Book Service entry for the user.</span></span> <span data-ttu-id="ff784-179">Le service de carnet d’adresses supprime toutes les images mises en cache toutes les 24 heures, ce qui signifie qu’il peut s’écouler jusqu’à 24 heures avant la mise à jour des nouvelles images utilisateur dans le cache du serveur.</span><span class="sxs-lookup"><span data-stu-id="ff784-179">The Address Book Service deletes all cached images every 24 hours, which means that it can take up to 24 hours for new user images to be updated in the cache on the server.</span></span> <span data-ttu-id="ff784-180">Vous pouvez forcer une mise à jour du cache à l’aide de l’applet de passe [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .</span><span class="sxs-lookup"><span data-stu-id="ff784-180">You can force an update to the cache by using the [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) cmdlet.</span></span>

<span data-ttu-id="ff784-181">Les photos des utilisateurs incluses dans le statut de présence possèdent également une valeur de hachage associée que le client Lync utilise pour déterminer si une nouvelle image est disponible.</span><span class="sxs-lookup"><span data-stu-id="ff784-181">User photos included in Presence status also have an associated hash value that Lync client uses to determine whether there is a newer image available.</span></span> <span data-ttu-id="ff784-182">Le client est automatiquement averti des modifications apportées au fichier image utilisé dans le statut de présence.</span><span class="sxs-lookup"><span data-stu-id="ff784-182">The client is automatically notified of changes to the image file used in Presence status.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="ff784-183">Étant donné que les photos ne sont pas stockées dans la base de données GalContacts. DB, le téléchargement des photos des utilisateurs ne dépend pas du paramètre <STRONG>AddressBookAvailability</STRONG> dans la stratégie client (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span><span class="sxs-lookup"><span data-stu-id="ff784-183">Because photos are not stored in the GalContacts.db database, downloading user photos is not dependent on the <STRONG>AddressBookAvailability</STRONG> setting in the client policy (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).</span></span>



</div>

<span data-ttu-id="ff784-184">La requête au service ABWQ inclut les attributs suivants :</span><span class="sxs-lookup"><span data-stu-id="ff784-184">The query to the ABWQ service includes the following attributes:</span></span>

  - <span data-ttu-id="ff784-185">**Photohachez**   la valeur de hachage des données de photo binaires et est utilisée pour déterminer si la photo actuelle a changé.</span><span class="sxs-lookup"><span data-stu-id="ff784-185">**PhotoHash**   The hash value of the binary photo data, and is used to determine whether the current photo has changed.</span></span>

  - <span data-ttu-id="ff784-186">**PhotoRelPath**   chemin d’accès relatif du fichier image stocké sur le serveur.</span><span class="sxs-lookup"><span data-stu-id="ff784-186">**PhotoRelPath**   The relative path to the image file stored on the server.</span></span>

  - <span data-ttu-id="ff784-187">**Photodimensionnez**   la taille du fichier image, en octets.</span><span class="sxs-lookup"><span data-stu-id="ff784-187">**PhotoSize**   The size of the image file, in bytes.</span></span>

  - <span data-ttu-id="ff784-188">\*\*\*\* Date et heure auxquelles le fichier image a été téléchargé en dernier du serveur et copié dans le cache du client.   </span><span class="sxs-lookup"><span data-stu-id="ff784-188">**TimeStamp**   The date and time at which the image file was last downloaded from the server and copied to the client cache.</span></span>

<span data-ttu-id="ff784-189">Ensuite, après avoir récupéré le fichier image, le client 2010 Lync compare les valeurs d’attribut renvoyées par la requête par rapport aux valeurs d’attributs reçues par le client à partir de la mise en service intrabande pour voir s’il est différent.</span><span class="sxs-lookup"><span data-stu-id="ff784-189">Next, after retrieving the image file, Lync 2010 client compares the attribute values returned from the query against the attribute values received by the client from in-band provisioning to see if they are different.</span></span> <span data-ttu-id="ff784-190">Si les valeurs sont différentes, le client récupère le fichier image de l’utilisateur connecté à l’aide d’une requête GET HTTP.</span><span class="sxs-lookup"><span data-stu-id="ff784-190">If the values are different, the client retrieves the image file of the signed-in user with an HTTP GET request.</span></span>

<span data-ttu-id="ff784-191">Par ailleurs, le client vérifie auprès du serveur toutes les 24 heures après l’heure de création de la version mise en cache du fichier image pour comparer la valeur de l’attribut **photodièse** sur le serveur avec la valeur sur le client.</span><span class="sxs-lookup"><span data-stu-id="ff784-191">Additionally, the client checks with the server every 24 hours from the time at which the cached version of the image file was created to compare the value of the **PhotoHash** attribute on the server with the value on the client.</span></span> <span data-ttu-id="ff784-192">Si les valeurs sont différentes, le client sait que le fichier image a changé.</span><span class="sxs-lookup"><span data-stu-id="ff784-192">If the values are different, the client knows that the image file has changed.</span></span> <span data-ttu-id="ff784-193">Pour obtenir le fichier image mis à jour, le client interroge de nouveau le service ABWQ pour mettre à jour le fichier image dans le cache du client avec le fichier image sur le serveur, ce qui réinitialise également l' **horodatage** sur le fichier dans le cache client.</span><span class="sxs-lookup"><span data-stu-id="ff784-193">To obtain the updated image file, the client again queries the ABWQ service to update the image file in the client cache with the image file on the server, which also resets the **TimeStamp** on the file in the client cache.</span></span>

<span data-ttu-id="ff784-194">Voici un exemple de réponse à une requête sur le service ABWQ :</span><span class="sxs-lookup"><span data-stu-id="ff784-194">The following is an example response to a query to the ABWQ service:</span></span>
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

## <a name="user-photos-in-lync-2013"></a><span data-ttu-id="ff784-195">Photos des utilisateurs dans Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ff784-195">User photos in Lync 2013</span></span>

<span data-ttu-id="ff784-196">Lync 2013 a mis en place une prise en charge des images haute résolution pour les photos des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ff784-196">Lync 2013 introduced support for high-resolution images for user photos.</span></span> <span data-ttu-id="ff784-197">Lync 2013 inclut également la prise en charge du stockage de photos des utilisateurs dans la boîte aux lettres de l’utilisateur sur Exchange 2013, qui supprime les limitations de résolution et de taille d’image présentes dans Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="ff784-197">Lync 2013 also includes support for storing user photos in the user's mailbox on Exchange 2013, which removes the image resolution and size limitations present in Lync 2010.</span></span> <span data-ttu-id="ff784-198">Les photos des utilisateurs dans Lync 2013 peuvent prendre jusqu’à 648 pixels par 648 pixels et disposer d’une taille de fichier pouvant atteindre 20 Mo.</span><span class="sxs-lookup"><span data-stu-id="ff784-198">User photos in Lync 2013 can be up to 648 pixels by 648 pixels with a file size of up to 20 MB.</span></span> <span data-ttu-id="ff784-199">Les photos haute résolution de Lync 2013 doivent figurer dans la boîte aux lettres de l’utilisateur sur Exchange 2013 et ne sont prises en charge que par le client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ff784-199">High-resolution photos in Lync 2013 must be located in the user's mailbox on Exchange 2013, and are supported only with Lync 2013 client.</span></span> <span data-ttu-id="ff784-200">Cette intégration avec Exchange tire parti de la nouvelle infrastructure d’autorisation incluse dans les versions 2013 de Lync, Exchange et SharePoint appelées OAuth.</span><span class="sxs-lookup"><span data-stu-id="ff784-200">This integration with Exchange takes advantage of the new authorization framework included in the 2013 versions of Lync, Exchange, and SharePoint called Oauth.</span></span>

<span data-ttu-id="ff784-201">Si Exchange 2013 n’est pas utilisé dans votre déploiement, la prise en charge des photos des utilisateurs est identique à celle de Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="ff784-201">If Exchange 2013 is not used in your deployment, support for user photos is the same as with Lync 2010.</span></span> <span data-ttu-id="ff784-202">Toutefois, les options utilisateur permettant de choisir la photo à utiliser diffèrent dans le client 2013 Lync.</span><span class="sxs-lookup"><span data-stu-id="ff784-202">However, the user options to choose the photo to use are different in Lync 2013 client.</span></span> <span data-ttu-id="ff784-203">Dans le client Lync 2013, les utilisateurs peuvent sélectionner l’option **Masquer mon image** ou **afficher mon image**.</span><span class="sxs-lookup"><span data-stu-id="ff784-203">In Lync 2013 client, users can select either **Hide my picture** or **Show my picture**.</span></span> <span data-ttu-id="ff784-204">L’option **afficher une image à partir d’un site Web** n’est pas disponible par défaut, mais peut être activée en assignant une stratégie client.</span><span class="sxs-lookup"><span data-stu-id="ff784-204">The option **Show a picture from a website** is not available by default, but can be enabled by assigning a client policy.</span></span>

<div>

## <a name="hide-my-picture"></a><span data-ttu-id="ff784-205">Masquer mon image</span><span class="sxs-lookup"><span data-stu-id="ff784-205">Hide my picture</span></span>

<span data-ttu-id="ff784-206">Les paramètres des photos des utilisateurs se trouvent dans la boîte de dialogue **options** de Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ff784-206">Settings for user photos are on the **Options** dialog in Lync 2013.</span></span> <span data-ttu-id="ff784-207">Lorsque vous sélectionnez **Masquer mon image**, aucune photo de l’utilisateur ne s’affiche dans le client Lync, mais votre photo est toujours affichée sur votre carte de visite et en dehors de Lync.</span><span class="sxs-lookup"><span data-stu-id="ff784-207">When you choose **Hide my picture**, no user photo is displayed for you in Lync client, but your photo is still displayed on your contact card and outside of Lync.</span></span>

</div>

<div>

## <a name="show-my-picture"></a><span data-ttu-id="ff784-208">Afficher mon image</span><span class="sxs-lookup"><span data-stu-id="ff784-208">Show my picture</span></span>

<span data-ttu-id="ff784-209">Lorsque vous sélectionnez l’option **afficher mon image** , la photo de l’utilisateur s’affiche dans votre client Lync et aux autres utilisateurs des conversations Lync.</span><span class="sxs-lookup"><span data-stu-id="ff784-209">When you choose the **Show my picture** option, your user photo is displayed in your Lync client and to other users in Lync conversations.</span></span> <span data-ttu-id="ff784-210">L’image utilisée est celle qui est stockée dans AD DS.</span><span class="sxs-lookup"><span data-stu-id="ff784-210">The image used is the one stored in AD DS.</span></span>

</div>

<div>

## <a name="show-a-picture-from-a-website"></a><span data-ttu-id="ff784-211">Afficher une image à partir d’un site Web</span><span class="sxs-lookup"><span data-stu-id="ff784-211">Show a picture from a website</span></span>

<span data-ttu-id="ff784-212">L’option **afficher l’image à partir d’un site Web** devient disponible dans Lync 2013 une fois qu’une stratégie client est définie pour l’activer.</span><span class="sxs-lookup"><span data-stu-id="ff784-212">The **Show picture from a website** option becomes available in Lync 2013 after a client policy is set to enable it.</span></span> <span data-ttu-id="ff784-213">La version cliente doit être plus récente que 15.0.4535.1002, installée avec les [mises à jour cumulatives de Lync : 2013 de novembre](http://go.microsoft.com/fwlink/p/?linkid=509908).</span><span class="sxs-lookup"><span data-stu-id="ff784-213">The client version must be newer than 15.0.4535.1002, which is installed with the [Lync Cumulative Updates: November 2013](http://go.microsoft.com/fwlink/p/?linkid=509908).</span></span> <span data-ttu-id="ff784-214">Les utilisateurs doivent se déconnecter, puis revenir de nouveau pour voir les modifications apportées au client.</span><span class="sxs-lookup"><span data-stu-id="ff784-214">Users may need to log out and then back in again to see the changes in the client.</span></span>

<span data-ttu-id="ff784-215">Vous pouvez configurer la stratégie client pour qu’elle soit activée pour **afficher une image à partir d’un site Web** en exécutant la stratégie [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) dans Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ff784-215">You can set the client policy to enable to **Show picture from a website** setting by running the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) policy in the Lync Server Management Shell.</span></span> <span data-ttu-id="ff784-216">Les exemples d’applets de commande suivants montrent comment définir globalement la stratégie pour tous les utilisateurs de votre déploiement :</span><span class="sxs-lookup"><span data-stu-id="ff784-216">The following example cmdlets demonstrate how to set the policy globally for all users in your deployment:</span></span>

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


<span data-ttu-id="ff784-217">Lorsqu’une image est téléchargée vers la boîte aux lettres de l’utilisateur, Exchange crée automatiquement une version de résolution plus basse de l’image qui peut être utilisée dans les applications clientes.</span><span class="sxs-lookup"><span data-stu-id="ff784-217">When an image is uploaded to the user’s mailbox, Exchange automatically creates a lower resolution version of the image which can be used in client applications.</span></span> <span data-ttu-id="ff784-218">La photo de l’utilisateur est également mise à jour dans AD DS.</span><span class="sxs-lookup"><span data-stu-id="ff784-218">The user photo is also updated in AD DS.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="ff784-219">Lors de la mise à jour d’un fichier image dans AD DS, une image de pixel 48 x 48 est créée et utilisée pour le thumbnailPhoto dans AD DS.</span><span class="sxs-lookup"><span data-stu-id="ff784-219">When an image file is updated in AD DS, a 48 x 48 pixel image is created and used for the thumbnailPhoto in AD DS.</span></span> <span data-ttu-id="ff784-220">Toute image existante est remplacée.</span><span class="sxs-lookup"><span data-stu-id="ff784-220">Any existing image is replaced.</span></span> <span data-ttu-id="ff784-221">Par conséquent, si vous avez ajouté une image 96 x 96 dans AD DS, celle-ci sera remplacée par la nouvelle image 48 x 48.</span><span class="sxs-lookup"><span data-stu-id="ff784-221">So if you added a 96 x 96 image to AD DS, it will be overwritten with the new 48 x 48 image.</span></span> <span data-ttu-id="ff784-222">Ce n’est pas seulement important : vous avez des utilisateurs dans votre environnement utilisant les clients Lync 2010, car ils obtiendront les photos des utilisateurs d’AD DS.</span><span class="sxs-lookup"><span data-stu-id="ff784-222">This is only important is you have users in your environment using Lync 2010 clients, as those clients will obtain user photos from AD DS.</span></span> <span data-ttu-id="ff784-223">Vous pouvez importer des images de 96 x 96 pixels pour remplacer celles créées par AD DS si vous avez des clients Lync 2010 au sein de votre organisation.</span><span class="sxs-lookup"><span data-stu-id="ff784-223">You can import 96 x 96 pixel images to replace the ones created by AD DS if you have Lync 2010 clients in your organization.</span></span>



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a><span data-ttu-id="ff784-224">Support photo de l’utilisateur dans Lync 2013</span><span class="sxs-lookup"><span data-stu-id="ff784-224">User photo support in Lync 2013</span></span>

<span data-ttu-id="ff784-225">Dans Lync 2013, trois résolutions d’image sont prises en charge pour les photos des utilisateurs, comme décrit dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="ff784-225">In Lync 2013, three image resolutions are supported for user photos as described in the following table.</span></span> <span data-ttu-id="ff784-226">L’image utilisée est déterminée par le paramètre de stratégie client attribué aux utilisateurs de Lync.</span><span class="sxs-lookup"><span data-stu-id="ff784-226">The image that is used is determined by the client policy setting assigned to Lync users.</span></span> <span data-ttu-id="ff784-227">Pour plus d’informations, voir la section « gestion de la photo de l’utilisateur avec les applets de stratégie client ».</span><span class="sxs-lookup"><span data-stu-id="ff784-227">See “Managing user’s photo with Client Policy cmdlets” in this topic for more information.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff784-228">Résolution d’image (pixels)</span><span class="sxs-lookup"><span data-stu-id="ff784-228">Image resolution (pixels)</span></span></th>
<th><span data-ttu-id="ff784-229">Application</span><span class="sxs-lookup"><span data-stu-id="ff784-229">Application</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff784-230">48 x 48</span><span class="sxs-lookup"><span data-stu-id="ff784-230">48 x 48</span></span></p></td>
<td><p><span data-ttu-id="ff784-231">Utilisé si aucune image de résolution plus élevée n’est sélectionnée</span><span class="sxs-lookup"><span data-stu-id="ff784-231">Used if no higher resolution image is selected</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff784-232">96 x 96</span><span class="sxs-lookup"><span data-stu-id="ff784-232">96 x 96</span></span></p></td>
<td><p><span data-ttu-id="ff784-233">Utilisé dans Outlook Web App et Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="ff784-233">Used in Outlook Web App and Outlook 2013</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff784-234">648 x 648</span><span class="sxs-lookup"><span data-stu-id="ff784-234">648 x 648</span></span></p></td>
<td><p><span data-ttu-id="ff784-235">Utilisé dans le client de bureau Lync 2013 et Lync 2013 Web App</span><span class="sxs-lookup"><span data-stu-id="ff784-235">Used in Lync 2013 desktop client and Lync 2013 Web App</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="ff784-236">Tout utilisateur disposant d’une boîte aux lettres activée dans Exchange 2013 peut télécharger une autre image, y compris des photos haute résolution, via les options client d’Outlook Web Access ou Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="ff784-236">Any user with a mailbox enabled in Exchange 2013 can upload a different image, including high-resolution photos, through Outlook Web Access or Lync 2013 client options.</span></span> <span data-ttu-id="ff784-237">Les paramètres recommandés pour les images utilisées sont les suivants :</span><span class="sxs-lookup"><span data-stu-id="ff784-237">The recommended settings for images used include:</span></span>

  - <span data-ttu-id="ff784-238">**Résolution d’image**   648 par 648 pixels</span><span class="sxs-lookup"><span data-stu-id="ff784-238">**Image Resolution**   648 by 648 pixels</span></span>

  - <span data-ttu-id="ff784-239">**Palette de couleurs**   24 bits</span><span class="sxs-lookup"><span data-stu-id="ff784-239">**Color Depth**   24-bit</span></span>

  - <span data-ttu-id="ff784-240">**Taille de fichier d’image**   maximale de 20 Mo</span><span class="sxs-lookup"><span data-stu-id="ff784-240">**Image file size**   up to 20 MB</span></span>

  - <span data-ttu-id="ff784-241">**Format de fichier**   JPEG</span><span class="sxs-lookup"><span data-stu-id="ff784-241">**File format**   JPEG</span></span>

<span data-ttu-id="ff784-242">Une image JPEG standard 24 bits d’une taille de 648 648 pixels, dont la taille est d’environ 240 Ko, est nécessaire pour les 4 Mo d’espace de stockage pour chaque photo de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="ff784-242">A typical 24-bit JPEG image that is 648 pixels by 648 pixels has a file size of about 240 KB, so 1 MB of storage space is needed for every 4 user photos.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

