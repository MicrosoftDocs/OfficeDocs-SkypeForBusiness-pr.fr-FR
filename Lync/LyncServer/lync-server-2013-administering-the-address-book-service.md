---
title: 'Lync Server 2013 : administration du service de carnet d’adresses'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Administering the Address Book Service
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429711(v=OCS.15)
ms:contentKeyID: 48184649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5d12b904cbb679b66579c7c669ba46e0d732034b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737974"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="c9217-102">Administration du service de carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c9217-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c9217-103">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="c9217-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="c9217-104">Dans le cadre du déploiement de Lync Server, Enterprise Edition ou Standard Edition Server, le service de carnet d’adresses est installé par défaut.</span><span class="sxs-lookup"><span data-stu-id="c9217-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="c9217-105">La base de données utilisée par le service de carnet d’adresses (RTCab) est créée sur SQL Server (pour Enterprise Edition, il s’agit du serveur principal SQL Server ; pour Standard Edition Server, serveur SQL colocalisé).</span><span class="sxs-lookup"><span data-stu-id="c9217-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9217-106">Pour plus d’informations sur l’utilisation de la <STRONG>modification ADSI</STRONG> pour modifier les attributs d’objet des services de domaine Active Directory, voir <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span><span class="sxs-lookup"><span data-stu-id="c9217-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="c9217-107">Pour plus d’informations sur un outil du kit de ressources pour le service de carnet d’adresses, voir <A href="http://go.microsoft.com/fwlink/?linkid=330429">outils du kit de ressources Microsoft Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="c9217-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="c9217-108">Normalisation des numéros de téléphone du serveur du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="c9217-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="c9217-109">Lync Server nécessite des numéros de téléphone RFC 3966/E. 164 normalisés.</span><span class="sxs-lookup"><span data-stu-id="c9217-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="c9217-110">Pour utiliser les numéros de téléphone non structurés ou structurés de manière incohérente, Lync Server s’appuie sur le serveur du carnet d’adresses pour prétraiter les numéros de téléphone avant d’être remis aux règles de normalisation.</span><span class="sxs-lookup"><span data-stu-id="c9217-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="c9217-111">Lorsque vous utilisez un numéro de téléphone à partir du carnet d’adresses et que la règle de normalisation est appliquée, les clients, tels que Lync Phone Edition et Lync mobile, peuvent utiliser ces numéros normalisés.</span><span class="sxs-lookup"><span data-stu-id="c9217-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="c9217-112">Les règles de normalisation utilisées dans les versions précédentes risquent de ne pas fonctionner correctement sans quelques ajustements.</span><span class="sxs-lookup"><span data-stu-id="c9217-112">The normalization rules that were used in previous versions may not work properly without some adjustments.</span></span> <span data-ttu-id="c9217-113">Dans la mesure où les caractères blancs et non obligatoires sont supprimés avant les règles de normalisation, si votre expression Regex recherche plus précisément un tiret ou un autre caractère supprimé, votre règle de normalisation peut échouer.</span><span class="sxs-lookup"><span data-stu-id="c9217-113">Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail.</span></span> <span data-ttu-id="c9217-114">Nous vous conseillons de passer en revue les règles de normalisation pour vous assurer qu’elles ne recherchent pas ces caractères non obligatoires, ou que la règle peut échouer de manière harmonieuse et poursuivre en cas d’absence du caractère au niveau de la règle.</span><span class="sxs-lookup"><span data-stu-id="c9217-114">You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="c9217-115">Serveur du carnet d’adresses et réplicateur d’utilisateurs</span><span class="sxs-lookup"><span data-stu-id="c9217-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="c9217-116">Le serveur du carnet d’adresses utilise les données fournies par le réplicateur d’utilisateurs pour mettre à jour les informations qu’il obtient initialement de la liste d’adresses globale.</span><span class="sxs-lookup"><span data-stu-id="c9217-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="c9217-117">Le réplicateur d’utilisateurs écrit les attributs des services de domaine Active Directory pour chaque utilisateur, contact et groupe dans la table AbUserEntry de la base de données, et le serveur du carnet d’adresses synchronise les données utilisateur de la base de données dans les fichiers du magasin de fichiers du serveur de carnet d’adresses et dans la base de données du RTCab.</span><span class="sxs-lookup"><span data-stu-id="c9217-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="c9217-118">Le schéma de la table AbUserEntry utilise deux colonnes, **UserGuid** et **UserData**.</span><span class="sxs-lookup"><span data-stu-id="c9217-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="c9217-119">**UserGuid** est la colonne d’index et contient le GUID de 16 octets de l’objet Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c9217-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="c9217-120">**UserData** est une colonne d’image qui contient tous les attributs de services de domaine Active Directory (AD FS) déjà mentionnés pour ce contact.</span><span class="sxs-lookup"><span data-stu-id="c9217-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="c9217-121">Le réplicateur d’utilisateurs détermine les attributs Active Directory à écrire en lisant une table de configuration située dans la même instance SQL Server que la table AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="c9217-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="c9217-122">La table AbAttribute contient trois colonnes, **ID**, **nom**, **indicateurs**et **activer**.</span><span class="sxs-lookup"><span data-stu-id="c9217-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="c9217-123">La table est créée lors de la configuration de la base de données.</span><span class="sxs-lookup"><span data-stu-id="c9217-123">The table is created during database setup.</span></span> <span data-ttu-id="c9217-124">Si la table AbAttribute est vide, le réplicateur d’utilisateurs ignore la logique de traitement de la table AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="c9217-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="c9217-125">Les attributs de serveur du carnet d’adresses sont dynamiques et extraits de la table AbAttribute, qui est initialement rédigée par le serveur du carnet d’adresses lorsque le serveur du carnet d’adresses est activé.</span><span class="sxs-lookup"><span data-stu-id="c9217-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="c9217-126">L’activation du serveur du carnet d’adresses remplit la table AbAttribute avec les valeurs figurant dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="c9217-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9217-127">ID</span><span class="sxs-lookup"><span data-stu-id="c9217-127">ID</span></span></th>
<th><span data-ttu-id="c9217-128">Nom</span><span class="sxs-lookup"><span data-stu-id="c9217-128">Name</span></span></th>
<th><span data-ttu-id="c9217-129">Indicateurs</span><span class="sxs-lookup"><span data-stu-id="c9217-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9217-130">1</span><span class="sxs-lookup"><span data-stu-id="c9217-130">1</span></span></p></td>
<td><p><span data-ttu-id="c9217-131">givenName</span><span class="sxs-lookup"><span data-stu-id="c9217-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="c9217-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="c9217-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-133">deuxième</span><span class="sxs-lookup"><span data-stu-id="c9217-133">2</span></span></p></td>
<td><p><span data-ttu-id="c9217-134">Perso</span><span class="sxs-lookup"><span data-stu-id="c9217-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="c9217-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="c9217-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-136">3</span><span class="sxs-lookup"><span data-stu-id="c9217-136">3</span></span></p></td>
<td><p><span data-ttu-id="c9217-137">displayName</span><span class="sxs-lookup"><span data-stu-id="c9217-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="c9217-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="c9217-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-139">4</span><span class="sxs-lookup"><span data-stu-id="c9217-139">4</span></span></p></td>
<td><p><span data-ttu-id="c9217-140">Titre</span><span class="sxs-lookup"><span data-stu-id="c9217-140">Title</span></span></p></td>
<td><p><span data-ttu-id="c9217-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="c9217-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-142">5</span><span class="sxs-lookup"><span data-stu-id="c9217-142">5</span></span></p></td>
<td><p><span data-ttu-id="c9217-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="c9217-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="c9217-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="c9217-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-145">6</span><span class="sxs-lookup"><span data-stu-id="c9217-145">6</span></span></p></td>
<td><p><span data-ttu-id="c9217-146">Elle</span><span class="sxs-lookup"><span data-stu-id="c9217-146">Company</span></span></p></td>
<td><p><span data-ttu-id="c9217-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="c9217-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-148">7</span><span class="sxs-lookup"><span data-stu-id="c9217-148">7</span></span></p></td>
<td><p><span data-ttu-id="c9217-149">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="c9217-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="c9217-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="c9217-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-151">version8</span><span class="sxs-lookup"><span data-stu-id="c9217-151">8</span></span></p></td>
<td><p><span data-ttu-id="c9217-152">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="c9217-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="c9217-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="c9217-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-154">09</span><span class="sxs-lookup"><span data-stu-id="c9217-154">9</span></span></p></td>
<td><p><span data-ttu-id="c9217-155">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="c9217-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="c9217-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="c9217-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-157">0,10</span><span class="sxs-lookup"><span data-stu-id="c9217-157">10</span></span></p></td>
<td><p><span data-ttu-id="c9217-158">homePhone</span><span class="sxs-lookup"><span data-stu-id="c9217-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="c9217-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="c9217-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-160">27,9</span><span class="sxs-lookup"><span data-stu-id="c9217-160">11</span></span></p></td>
<td><p><span data-ttu-id="c9217-161">Mobile</span><span class="sxs-lookup"><span data-stu-id="c9217-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="c9217-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="c9217-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-163">midi</span><span class="sxs-lookup"><span data-stu-id="c9217-163">12</span></span></p></td>
<td><p><span data-ttu-id="c9217-164">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="c9217-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="c9217-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="c9217-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-166">n°13</span><span class="sxs-lookup"><span data-stu-id="c9217-166">13</span></span></p></td>
<td><p><span data-ttu-id="c9217-167">ipPhone</span><span class="sxs-lookup"><span data-stu-id="c9217-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="c9217-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="c9217-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-169">14</span><span class="sxs-lookup"><span data-stu-id="c9217-169">14</span></span></p></td>
<td><p><span data-ttu-id="c9217-170">Fonctionnalité</span><span class="sxs-lookup"><span data-stu-id="c9217-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="c9217-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="c9217-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-172">0,15</span><span class="sxs-lookup"><span data-stu-id="c9217-172">15</span></span></p></td>
<td><p><span data-ttu-id="c9217-173">groupType</span><span class="sxs-lookup"><span data-stu-id="c9217-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="c9217-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="c9217-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-175">Seiz</span><span class="sxs-lookup"><span data-stu-id="c9217-175">16</span></span></p></td>
<td><p><span data-ttu-id="c9217-176">Service</span><span class="sxs-lookup"><span data-stu-id="c9217-176">Department</span></span></p></td>
<td><p><span data-ttu-id="c9217-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="c9217-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-178">Play</span><span class="sxs-lookup"><span data-stu-id="c9217-178">17</span></span></p></td>
<td><p><span data-ttu-id="c9217-179">Description</span><span class="sxs-lookup"><span data-stu-id="c9217-179">Description</span></span></p></td>
<td><p><span data-ttu-id="c9217-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="c9217-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-181">19</span><span class="sxs-lookup"><span data-stu-id="c9217-181">18</span></span></p></td>
<td><p><span data-ttu-id="c9217-182">Responsable</span><span class="sxs-lookup"><span data-stu-id="c9217-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="c9217-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="c9217-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-184">19,6</span><span class="sxs-lookup"><span data-stu-id="c9217-184">19</span></span></p></td>
<td><p><span data-ttu-id="c9217-185">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="c9217-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="c9217-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="c9217-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-187">CX3-20</span><span class="sxs-lookup"><span data-stu-id="c9217-187">20</span></span></p></td>
<td><p><span data-ttu-id="c9217-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="c9217-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="c9217-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="c9217-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-190">99</span><span class="sxs-lookup"><span data-stu-id="c9217-190">99</span></span></p></td>
<td><p><span data-ttu-id="c9217-191">Identificateur</span><span class="sxs-lookup"><span data-stu-id="c9217-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="c9217-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="c9217-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c9217-193">Les nombres de la colonne **ID** doivent être uniques et ne doivent jamais être réutilisés.</span><span class="sxs-lookup"><span data-stu-id="c9217-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="c9217-194">En outre, le fait de maintenir les valeurs d’identification sous 256 économise de l’espace dans les fichiers de sortie écrits par le serveur du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="c9217-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="c9217-195">Toutefois, la valeur d’ID maximale est 65535.</span><span class="sxs-lookup"><span data-stu-id="c9217-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="c9217-196">La colonne **Name** correspond au nom de l’attribut Active Directory que le réplicateur d’utilisateurs doit placer dans la table AbUserEntry de chaque contact.</span><span class="sxs-lookup"><span data-stu-id="c9217-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="c9217-197">La valeur de la colonne **indicateurs** permet de définir le type d’attribut.</span><span class="sxs-lookup"><span data-stu-id="c9217-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="c9217-198">Les types suivants de valeurs de serveur de carnet d’adresses sont reconnus par User Replicator, indiqués par le poids faible de la valeur dans la colonne **indicateurs** .</span><span class="sxs-lookup"><span data-stu-id="c9217-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9217-199">Attribut</span><span class="sxs-lookup"><span data-stu-id="c9217-199">Attribute</span></span></th>
<th><span data-ttu-id="c9217-200">Description</span><span class="sxs-lookup"><span data-stu-id="c9217-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9217-201">0x0</span><span class="sxs-lookup"><span data-stu-id="c9217-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="c9217-202">Un attribut de chaîne.</span><span class="sxs-lookup"><span data-stu-id="c9217-202">A string attribute.</span></span> <span data-ttu-id="c9217-203">Le réplicateur d’utilisateurs convertit ce type en UTF-8 avant de le stocker dans la table AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="c9217-203">User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-204">0x1</span><span class="sxs-lookup"><span data-stu-id="c9217-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="c9217-205">Un attribut binaire.</span><span class="sxs-lookup"><span data-stu-id="c9217-205">A binary attribute.</span></span> <span data-ttu-id="c9217-206">Le réplicateur d’utilisateurs enregistre cela dans l’objet BLOB sans conversion.</span><span class="sxs-lookup"><span data-stu-id="c9217-206">User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-207">0X2</span><span class="sxs-lookup"><span data-stu-id="c9217-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="c9217-208">Un attribut de chaîne, mais est inclus uniquement si la valeur de l' &quot;attribut commence&quot;par tel :.</span><span class="sxs-lookup"><span data-stu-id="c9217-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="c9217-209">Cela s’adresse principalement aux attributs de chaîne à valeurs multiples, en particulier <strong>proxyAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="c9217-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="c9217-210">Dans ce cas, le serveur du carnet d’adresses est <strong></strong> intéressé uniquement dans les entrées &quot;proxyAddresses qui&quot;commencent par la lettre « tel : ».</span><span class="sxs-lookup"><span data-stu-id="c9217-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="c9217-211">Par conséquent, pour économiser de l’espace, le réplicateur d’utilisateurs stocke uniquement les entrées &quot;qui commencent&quot;par tel :.</span><span class="sxs-lookup"><span data-stu-id="c9217-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-212">0x3</span><span class="sxs-lookup"><span data-stu-id="c9217-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="c9217-213">Un attribut de chaîne booléenne, qui, si TRUE, le réplicateur de utilisateurs n’inclura pas ce contact dans la table AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="c9217-213">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table.</span></span> <span data-ttu-id="c9217-214">Si la valeur est FALSe, le réplicateur d’utilisateurs doit inclure les attributs pour ce contact dans la table AbUserEntry, mais pas l’attribut particulier avec cet indicateur.</span><span class="sxs-lookup"><span data-stu-id="c9217-214">If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag.</span></span> <span data-ttu-id="c9217-215">Il s’agit d’un autre type de cas particulier qui est essentiellement destiné à l’attribut <strong>msExchHideFromAddressLists</strong> .</span><span class="sxs-lookup"><span data-stu-id="c9217-215">This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-216">0x4</span><span class="sxs-lookup"><span data-stu-id="c9217-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="c9217-217">Un attribut de chaîne, mais est inclus uniquement si la valeur de l' &quot;attribut commence&quot; par SMTP : &quot; @ &quot; et inclut le symbole.</span><span class="sxs-lookup"><span data-stu-id="c9217-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-218">0x5</span><span class="sxs-lookup"><span data-stu-id="c9217-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="c9217-219">Un attribut de chaîne, mais est inclus uniquement si la valeur de l’attribut &quot;commence par&quot; tel &quot;: ou&quot; SMTP : et &quot; @ &quot; inclut le symbole.</span><span class="sxs-lookup"><span data-stu-id="c9217-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-220">0x100</span><span class="sxs-lookup"><span data-stu-id="c9217-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="c9217-221">S’il est défini, il s’agit d’un attribut à valeurs multiples qui peut apparaître plusieurs fois pour chaque contact.</span><span class="sxs-lookup"><span data-stu-id="c9217-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-222">0x400</span><span class="sxs-lookup"><span data-stu-id="c9217-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="c9217-223">Si cette valeur est définie, elle identifie l’attribut du nom de compte d’utilisateur de messagerie d’un contact.</span><span class="sxs-lookup"><span data-stu-id="c9217-223">If set, this identifies the email user account name attribute for a contact.</span></span> <span data-ttu-id="c9217-224">Le serveur du carnet d’adresses utilise cet indicateur pour identifier la valeur d’attribut à afficher dans l’entrée du journal des événements de normalisation du téléphone.</span><span class="sxs-lookup"><span data-stu-id="c9217-224">Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-225">0x800</span><span class="sxs-lookup"><span data-stu-id="c9217-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="c9217-226">Si cette valeur est définie, elle identifie un attribut obligatoire pour un contact.</span><span class="sxs-lookup"><span data-stu-id="c9217-226">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="c9217-227">Le serveur du carnet d’adresses inclut un utilisateur dans la table AbUserEntry uniquement s’il existe une valeur pour cet attribut dans Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c9217-227">Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory.</span></span> <span data-ttu-id="c9217-228">S’il existe plusieurs attributs obligatoires, un seul d’eux est requis pour inclure une valeur dans la table AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="c9217-228">If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-229">0x1000</span><span class="sxs-lookup"><span data-stu-id="c9217-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="c9217-230">S’il est défini, le serveur du carnet d’adresses normalise toujours la valeur de cet attribut.</span><span class="sxs-lookup"><span data-stu-id="c9217-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-231">0x2000</span><span class="sxs-lookup"><span data-stu-id="c9217-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="c9217-232">S’il est défini, le serveur du carnet d’adresses utilise le numéro normalisé de <strong>proxyAddresses</strong>, si le paramètre <strong>UseNormalizationRules</strong> CMS a la valeur false. Sinon, il a le même comportement que lorsque le bit de l’indicateur est 0x1000.</span><span class="sxs-lookup"><span data-stu-id="c9217-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="c9217-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="c9217-234">S’il est défini, le serveur du carnet d’adresses n’inclut pas les objets dans la table AbUserEntry qui ont cette valeur pour l’attribut spécifié.</span><span class="sxs-lookup"><span data-stu-id="c9217-234">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute.</span></span> <span data-ttu-id="c9217-235">Par exemple, si l’attribut <strong>msRTCSIP-PrimaryUserAddress</strong> est défini pour ce bit d’indicateur, les contacts qui ont cet attribut ne sont pas écrits dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c9217-235">For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-236">vert</span><span class="sxs-lookup"><span data-stu-id="c9217-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="c9217-237">S’il est défini, le serveur du carnet d’adresses n’inclut pas d’objets dans la table AbUserEntry qui n’ont pas cette valeur pour l’attribut spécifié.</span><span class="sxs-lookup"><span data-stu-id="c9217-237">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute.</span></span> <span data-ttu-id="c9217-238">Si les bits d’indicateur 0x4000 et 0x8000 sont définis sur un objet, l’attribut avec la valeur de bit Flag définie sur 0x4000 a la priorité et l’objet est exclu de la table AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="c9217-238">If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="c9217-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="c9217-240">S’il est défini, il s’agit d’un objet de groupe.</span><span class="sxs-lookup"><span data-stu-id="c9217-240">If set, this represents a group object.</span></span> <span data-ttu-id="c9217-241">Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour inclure les contacts avec l’attribut <strong>GroupType</strong> dont la présence indique un groupe (par exemple, une liste de distribution ou un groupe de sécurité).</span><span class="sxs-lookup"><span data-stu-id="c9217-241">User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="c9217-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="c9217-243">S’il est défini, le réplicateur d’utilisateurs utilise ce bit d’indicateur pour inclure cet attribut dans les fichiers serveur du carnet d’adresses spécifiques à l’appareil (c’est-à-dire, les fichiers avec l’extension. dabs).</span><span class="sxs-lookup"><span data-stu-id="c9217-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c9217-244">Dans les versions précédentes de Lync Server, lors de l’application d’une modification à Active Directory, l’administrateur est tenu d’exécuter **Update-CSUserDatabase** et **Update-CSAddressBook** des cmdlets Windows PowerShell pour persister la modification de la base de données utilisateur et de la base de données RTCab du serveur Lync.</span><span class="sxs-lookup"><span data-stu-id="c9217-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="c9217-245">Dans Lync Server 2013, le réplicateur d’utilisateurs de Lync Server capte les modifications d’Active Directory et met à jour la base de données utilisateur de Lync Server en fonction d’un intervalle configuré.</span><span class="sxs-lookup"><span data-stu-id="c9217-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="c9217-246">Le réplicateur d’utilisateurs de Lync Server propage également les modifications apportées à la base de données RTCab sans qu’il soit nécessaire d’exécuter Update-CSAddressBook.</span><span class="sxs-lookup"><span data-stu-id="c9217-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="c9217-247">Si la requête Web du carnet d’adresses est activée, les modifications sont répercutées dans les résultats de recherche par les clients Lync.</span><span class="sxs-lookup"><span data-stu-id="c9217-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="c9217-248">Les administrateurs devront uniquement exécuter Update-CSAddressBook si le téléchargement du fichier du carnet d’adresses est activé.</span><span class="sxs-lookup"><span data-stu-id="c9217-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9217-249">Par défaut, le réplicateur d’utilisateurs de Lync Server s’exécute automatiquement toutes les cinq minutes.</span><span class="sxs-lookup"><span data-stu-id="c9217-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="c9217-250">Vous pouvez configurer cet intervalle à l’aide de Set-CSUserReplicatorConfiguration &lt; &gt;-ReplicationCycleInterval.</span><span class="sxs-lookup"><span data-stu-id="c9217-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="c9217-251">Filtrage du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="c9217-251">Filtering the Address Book</span></span>

<span data-ttu-id="c9217-252">Les utilisateurs remplis dans les fichiers du serveur du carnet d’adresses peuvent être contrôlés en fonction de certains attributs de services de domaine Active Directory, répertoriés dans la table abattribut.</span><span class="sxs-lookup"><span data-stu-id="c9217-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="c9217-253">Il s’agit de l’attribut **msExchangeHideFromAddressBook** utilisé pour le filtrage.</span><span class="sxs-lookup"><span data-stu-id="c9217-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="c9217-254">Il s’agit d’un attribut utilisateur ajouté par le schéma Exchange.</span><span class="sxs-lookup"><span data-stu-id="c9217-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="c9217-255">Si la valeur de cet attribut est TRUE, Exchange Server utilise cet attribut pour masquer le contact dans la liste d’adresses globale Outlook.</span><span class="sxs-lookup"><span data-stu-id="c9217-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="c9217-256">De même, si la valeur de cet attribut est TRUE, le réplicateur d’utilisateurs n’inclut pas cet utilisateur dans la table AbUserEntry, et cet utilisateur ne se trouve pas dans les fichiers du serveur du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="c9217-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="c9217-257">Vous pouvez utiliser certains bits d’indicateur pour définir un filtre à utiliser sur les attributs du serveur du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="c9217-257">You can use some flag bits to define a filter to use on Address Book Server attributes.</span></span> <span data-ttu-id="c9217-258">Par exemple, la présence de certains bits d’indicateur peut identifier un attribut en tant qu’attribut include ou attribut exclude.</span><span class="sxs-lookup"><span data-stu-id="c9217-258">For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute.</span></span> <span data-ttu-id="c9217-259">Le réplicateur d’utilisateurs filtre les contacts qui contiennent un attribut exclude et filtres qui ne contiennent pas d’attribut include.</span><span class="sxs-lookup"><span data-stu-id="c9217-259">User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="c9217-260">Pour plus d’informations sur le filtrage du carnet d’adresses, voir <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">applets de filtre d’adresses serveur dans Lync Server 2013</A>et <A href="http://go.microsoft.com/fwlink/?linkid=330430">filtrer le carnet d’adresses Lync 2013</A></span><span class="sxs-lookup"><span data-stu-id="c9217-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="c9217-261">Il existe actuellement trois filtres différents.</span><span class="sxs-lookup"><span data-stu-id="c9217-261">Currently, there are three different filters.</span></span> <span data-ttu-id="c9217-262">Le tableau suivant répertorie ces filtres.</span><span class="sxs-lookup"><span data-stu-id="c9217-262">The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c9217-263">Attribut</span><span class="sxs-lookup"><span data-stu-id="c9217-263">Attribute</span></span></th>
<th><span data-ttu-id="c9217-264">Description</span><span class="sxs-lookup"><span data-stu-id="c9217-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c9217-265">0x800</span><span class="sxs-lookup"><span data-stu-id="c9217-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="c9217-266">Si cette valeur est définie, elle identifie un attribut obligatoire pour un contact.</span><span class="sxs-lookup"><span data-stu-id="c9217-266">If set, this identifies a required attribute for a contact.</span></span> <span data-ttu-id="c9217-267">Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour filtrer les contacts qui ne contiennent pas au moins un attribut obligatoire.</span><span class="sxs-lookup"><span data-stu-id="c9217-267">User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute.</span></span> <span data-ttu-id="c9217-268">OuPathId est un attribut obligatoire, qui est toujours défini.</span><span class="sxs-lookup"><span data-stu-id="c9217-268">The OuPathId is a required attribute, which is always set.</span></span> <span data-ttu-id="c9217-269">Pour pouvoir définir au moins un des autres attributs obligatoires.</span><span class="sxs-lookup"><span data-stu-id="c9217-269">So at least one of other required attributes should be set.</span></span> <span data-ttu-id="c9217-270">Dans le cas contraire, le contact (c’est-à-dire, avec la valeur de l’attribut requis OuPathId) ne sera toujours pas écrit dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c9217-270">Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database.</span></span> <span data-ttu-id="c9217-271">Par exemple, si <strong>telephoneNumber</strong> et <strong>homePhone</strong> sont définis comme attributs obligatoires, seuls les contacts qui ont au moins un de ces attributs sont écrits dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c9217-271">For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c9217-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="c9217-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="c9217-273">Si cette valeur est définie, elle identifie un attribut exclude.</span><span class="sxs-lookup"><span data-stu-id="c9217-273">If set, this identifies an exclude attribute.</span></span> <span data-ttu-id="c9217-274">Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour filtrer les contacts qui contiennent cet attribut.</span><span class="sxs-lookup"><span data-stu-id="c9217-274">User Replicator uses this flag bit to filter out contacts that contain this attribute.</span></span> <span data-ttu-id="c9217-275">Par exemple, si <strong>msRTCSIP-PrimaryUserAddress</strong> est défini en tant qu’attribut exclude, les contacts qui ont cet attribut ne sont pas écrits dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c9217-275">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c9217-276">vert</span><span class="sxs-lookup"><span data-stu-id="c9217-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="c9217-277">Si cette valeur est définie, elle identifie un attribut include.</span><span class="sxs-lookup"><span data-stu-id="c9217-277">If set, this identifies an include attribute.</span></span> <span data-ttu-id="c9217-278">Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour filtrer les contacts qui ne contiennent pas cet attribut.</span><span class="sxs-lookup"><span data-stu-id="c9217-278">User Replicator uses this flag bit to filter out contacts that do not contain this attribute.</span></span> <span data-ttu-id="c9217-279">Par exemple, si <strong>msRTCSIP-PrimaryUserAddress</strong> est défini comme attribut include, seuls les contacts dotés de cet attribut sont écrits dans la base de données.</span><span class="sxs-lookup"><span data-stu-id="c9217-279">For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c9217-280">Si les bits d’indicateur 0x4000 (Exclude) et 0x8000 (include Attribute) sont définis, le bit 0x4000 remplace le bit 0x8000 et le contact est exclu.</span><span class="sxs-lookup"><span data-stu-id="c9217-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="c9217-281">Même si vous pouvez filtrer le carnet d’adresses pour inclure uniquement certains utilisateurs, le fait de limiter les entrées ne limite pas la capacité des utilisateurs à contacter les utilisateurs filtrés ou à voir leur statut de présence.</span><span class="sxs-lookup"><span data-stu-id="c9217-281">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status.</span></span> <span data-ttu-id="c9217-282">Les utilisateurs peuvent toujours retrouver, envoyer des messages instantanés manuellement ou lancer manuellement des appels vers des utilisateurs qui ne se trouvent pas dans le carnet d’adresses en entrant le nom de connexion complet d’un utilisateur.</span><span class="sxs-lookup"><span data-stu-id="c9217-282">Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name.</span></span> <span data-ttu-id="c9217-283">Vous pouvez également consulter les informations de contact d’un utilisateur dans Outlook.</span><span class="sxs-lookup"><span data-stu-id="c9217-283">Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="c9217-284">Lorsque vous avez des enregistrements de contact complets dans les fichiers du carnet d’adresses vous permet d’utiliser Lync Server pour lancer le courrier électronique, le téléphone ou les appels vocaux d’entreprise (autrement dit, si Enterprise Voice est activé sur le serveur) avec des utilisateurs qui ne sont pas configurés pour le lancement de la session Protocole (SIP), certaines organisations préfèrent inclure uniquement les utilisateurs compatibles SIP dans les entrées du serveur du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="c9217-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="c9217-285">Vous pouvez filtrer le carnet d’adresses pour inclure uniquement les utilisateurs compatibles SIP en effaçant le bit de 0x800 dans la colonne **indicateurs** des attributs obligatoires suivants : **mailnickname**, **telephoneNumber**, **homePhone**et **mobile**.</span><span class="sxs-lookup"><span data-stu-id="c9217-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="c9217-286">Vous pouvez également filtrer le carnet d’adresses pour inclure uniquement les utilisateurs compatibles SIP en définissant l’attribut 0x8000 (Include) dans la colonne **Flags** de l’attribut **msRTCSIP-PrimaryUserAddress** .</span><span class="sxs-lookup"><span data-stu-id="c9217-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="c9217-287">Cela permet également d’exclure les comptes de service des fichiers du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="c9217-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="c9217-288">Après avoir modifié la table AbAttribute, vous pouvez actualiser les données de la table AbUserEntry en exécutant la commande **Update-CsUserDatabase** de l’applet de commande.</span><span class="sxs-lookup"><span data-stu-id="c9217-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="c9217-289">Après la réplication du RÉPLICATEUR d’annuaires, vous pouvez mettre à jour le fichier dans le magasin de fichiers du serveur de carnet d’adresses en exécutant manuellement la commande cmdlet **UpdateCsAddressBook** .</span><span class="sxs-lookup"><span data-stu-id="c9217-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c9217-290">Le serveur frontal sur lequel le serveur du carnet d’adresses est placé ne peut pas être configuré par l’administratif.</span><span class="sxs-lookup"><span data-stu-id="c9217-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="c9217-291">L’un d’eux est choisi lors du déploiement — généralement, le premier serveur frontal déployé.</span><span class="sxs-lookup"><span data-stu-id="c9217-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="c9217-292">En cas d’échec, le service de carnet d’adresses va basculer vers un autre serveur frontal et ne requiert aucune intervention de l’administrateur.</span><span class="sxs-lookup"><span data-stu-id="c9217-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c9217-293">Si vous avez consolidé ou modifié votre infrastructure par le biais d’un déploiement de forêts multiples ou d’un déploiement parent/enfant (par exemple, la consolidation de votre infrastructure avant de migrer vers Lync Server), il est possible que le téléchargement du service de carnet d’adresses et la requête Web du carnet d’adresses échouent pour certains utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="c9217-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="c9217-294">Dans un déploiement incluant plusieurs domaines ou forêts, l’attribut <STRONG>MsRTCSIP-OriginatorSid</STRONG> est rempli sur les objets utilisateur qui présentent le problème.</span><span class="sxs-lookup"><span data-stu-id="c9217-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="c9217-295">Pour résoudre le problème, l’attribut <STRONG>MsRTCSIP-OriginatorSid</STRONG> doit être défini sur la valeur null.</span><span class="sxs-lookup"><span data-stu-id="c9217-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

