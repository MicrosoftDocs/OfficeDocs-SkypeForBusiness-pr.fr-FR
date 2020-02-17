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
ms.openlocfilehash: 4ea7a68d77acd7bbaf3de43fce38c0e85c02dad4
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037274"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="administering-the-address-book-service-in-lync-server-2013"></a><span data-ttu-id="0808e-102">Administration du service de carnet d’adresses dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0808e-102">Administering the Address Book Service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0808e-103">_**Dernière modification de la rubrique :** 2014-02-05_</span><span class="sxs-lookup"><span data-stu-id="0808e-103">_**Topic Last Modified:** 2014-02-05_</span></span>

<span data-ttu-id="0808e-104">Dans le cadre du déploiement de Lync Server, Enterprise Edition ou Standard Edition Server, le service de carnet d’adresses est installé par défaut.</span><span class="sxs-lookup"><span data-stu-id="0808e-104">As a part of the deployment of Lync Server, Enterprise Edition or Standard Edition server, the Address Book Service is installed by default.</span></span> <span data-ttu-id="0808e-105">La base de données utilisée par le service de carnet d’adresses – RTCab – est créée sur SQL Server (pour Enterprise Edition, il s’agit du serveur principal SQL Server ; pour le serveur Standard Edition, le serveur SQL colocalisé).</span><span class="sxs-lookup"><span data-stu-id="0808e-105">The database used by the Address Book Service – RTCab – is created on the SQL Server (for Enterprise Edition, this is the back-end SQL Server; for Standard Edition server, the collocated SQL Server).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0808e-106">Pour plus d’informations sur l’utilisation d' <STRONG>ADSI Edit</STRONG> pour modifier les attributs d’objet des services de domaine Active Directory, voir <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span><span class="sxs-lookup"><span data-stu-id="0808e-106">For information about using <STRONG>ADSI Edit</STRONG> to edit Active Directory Domain Services object attributes, see <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>.</span></span> <span data-ttu-id="0808e-107">Pour plus d’informations sur un outil dans le kit de ressources spécifiquement pour le service de carnet d’adresses, voir les <A href="http://go.microsoft.com/fwlink/?linkid=330429">outils du kit de ressources Microsoft Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="0808e-107">For information about a tool in the Resource Kit specifically for the Address Book service, see <A href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</A>.</span></span>



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a><span data-ttu-id="0808e-108">Normalisation des numéros de téléphone du serveur de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="0808e-108">Address Book Server Phone Number Normalization</span></span>

<span data-ttu-id="0808e-109">Lync Server requiert des numéros de téléphone RFC 3966/E. 164 standardisés.</span><span class="sxs-lookup"><span data-stu-id="0808e-109">Lync Server requires standardized RFC 3966/E.164 phone numbers.</span></span> <span data-ttu-id="0808e-110">Pour utiliser des numéros de téléphone non structurés ou mis en forme de manière incohérente, Lync Server s’appuie sur le serveur de carnet d’adresses pour prétraiter les numéros de téléphone avant qu’ils ne soient remis aux règles de normalisation.</span><span class="sxs-lookup"><span data-stu-id="0808e-110">To use phone numbers that are unstructured or inconsistently formatted, Lync Server relies on the Address Book Server to preprocess phone numbers before they are handed off to the normalization rules.</span></span> <span data-ttu-id="0808e-111">Lorsqu’un numéro de téléphone est utilisé à partir du carnet d’adresses et que la règle de normalisation est appliquée, les clients, tels que Lync Phone Edition et Lync mobile, peuvent utiliser ces nombres normalisés.</span><span class="sxs-lookup"><span data-stu-id="0808e-111">When a phone number is used from the address book and the normalization rule is applied, clients, such as Lync Phone Edition and Lync Mobile, can use these normalized numbers.</span></span>

<span data-ttu-id="0808e-p104">Les règles de normalisation utilisées dans les versions précédentes risquent de ne pas fonctionner correctement sans quelques ajustements. Du fait que les espaces et les caractères non obligatoires sont supprimés avant d’appliquer les règles de normalisation, si votre expression regex recherche spécifiquement un tiret ou tout autre caractère ayant été supprimé, votre règle de normalisation risque d’échouer. Vous devriez passer en revue vos règles de normalisation pour vous assurer qu’elles ne recherchent pas ces caractères non obligatoires, ou que la règle peut échouer normalement et se poursuivre au cas où le caractère soit absent et que la règle anticipe sa présence.</span><span class="sxs-lookup"><span data-stu-id="0808e-p104">The normalization rules that were used in previous versions may not work properly without some adjustments. Because the white space and non-mandatory characters are removed prior to the normalization rules, if your regex expression is specifically looking for a dash or other character that was removed, your normalization rule might fail. You should review your normalization rules to ensure that either they are not looking for these non-mandatory characters, or that the rule can fail gracefully and continue in the event that the character is not present where the rule anticipates it will be.</span></span>

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a><span data-ttu-id="0808e-115">Réplicateur d’utilisateurs et serveur de carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="0808e-115">User Replicator and Address Book Server</span></span>

<span data-ttu-id="0808e-116">Le serveur de carnet d’adresses utilise les données fournies par le réplicateur d’utilisateurs pour mettre à jour les informations obtenues initialement de la liste d’adresses globale.</span><span class="sxs-lookup"><span data-stu-id="0808e-116">The Address Book Server uses data provided by User Replicator to update the information that it initially obtains from the global address list (GAL).</span></span> <span data-ttu-id="0808e-117">Le réplicateur d’utilisateurs écrit les attributs des services de domaine Active Directory pour chaque utilisateur, contact et groupe dans la table AbUserEntry de la base de données et le serveur de carnet d’adresses synchronise les données utilisateur de la base de données avec les fichiers du magasin de fichiers du serveur de carnet d’adresses et dans la base de données du carnet d’adresses RTCab.</span><span class="sxs-lookup"><span data-stu-id="0808e-117">User Replicator writes the Active Directory Domain Services attributes for each user, contact, and group into the AbUserEntry table in the database and the Address Book Server syncs the user data from the database into files in the Address Book Server file store and into the Address Book database RTCab.</span></span> <span data-ttu-id="0808e-118">Le schéma pour la table AbUserEntry utilise deux colonnes : **Guid utilisateur** et **Données utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="0808e-118">The schema for the AbUserEntry table uses two columns, **UserGuid** and **UserData**.</span></span> <span data-ttu-id="0808e-119">**UserGuid** est la colonne d’index et contient le GUID de 16 octets de l’objet Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0808e-119">**UserGuid** is the index column and contains the 16-byte GUID of the Active Directory object.</span></span> <span data-ttu-id="0808e-120">**UserData** est une colonne d’image qui contient tous les attributs des services de domaine Active Directory mentionnés précédemment pour ce contact.</span><span class="sxs-lookup"><span data-stu-id="0808e-120">**UserData** is an image column which contains all of the previously mentioned Active Directory Domain Services attributes for that contact.</span></span>

<span data-ttu-id="0808e-121">Le réplicateur d’utilisateurs détermine les attributs Active Directory à écrire en lisant une table de configuration située dans la même instance SQL Server que la table AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="0808e-121">User Replicator determines which Active Directory attributes to write by reading a configuration table located in the same SQL Server-based instance as the AbUserEntry table.</span></span> <span data-ttu-id="0808e-122">La table AbAttribute contient trois colonnes : **ID**, **Nom**, **Indicateurs**et **Activer**.</span><span class="sxs-lookup"><span data-stu-id="0808e-122">The AbAttribute table contains three columns, **ID**, **Name**, **Flags**, and **Enable**.</span></span> <span data-ttu-id="0808e-123">La table est créée pendant la configuration de la base de données.</span><span class="sxs-lookup"><span data-stu-id="0808e-123">The table is created during database setup.</span></span> <span data-ttu-id="0808e-124">Si la table AbAttribute est vide, le réplicateur d’utilisateurs ignore la logique de traitement de sa table AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="0808e-124">If the AbAttribute table is empty, User Replicator skips its AbUserEntry table processing logic.</span></span> <span data-ttu-id="0808e-125">Les attributs du serveur de carnet d’adresses sont dynamiques et récupérés à partir de la table AbAttribute, qui est créée initialement par le serveur de carnet d’adresses à l’activation de ce dernier.</span><span class="sxs-lookup"><span data-stu-id="0808e-125">Address Book Server attributes are dynamic and are retrieved from the AbAttribute table, which is initially written by the Address Book Server when the Address Book Server is activated.</span></span>

<span data-ttu-id="0808e-126">L’activation du serveur de carnet d’adresses remplit la table AbAttribute avec les valeurs indiquées dans le tableau suivant.</span><span class="sxs-lookup"><span data-stu-id="0808e-126">Address Book Server activation populates the AbAttribute table with the values shown in the following table.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0808e-127">ID</span><span class="sxs-lookup"><span data-stu-id="0808e-127">ID</span></span></th>
<th><span data-ttu-id="0808e-128">Nom</span><span class="sxs-lookup"><span data-stu-id="0808e-128">Name</span></span></th>
<th><span data-ttu-id="0808e-129">Flags</span><span class="sxs-lookup"><span data-stu-id="0808e-129">Flags</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0808e-130">0,1</span><span class="sxs-lookup"><span data-stu-id="0808e-130">1</span></span></p></td>
<td><p><span data-ttu-id="0808e-131">givenName</span><span class="sxs-lookup"><span data-stu-id="0808e-131">givenName</span></span></p></td>
<td><p><span data-ttu-id="0808e-132">0x01400000</span><span class="sxs-lookup"><span data-stu-id="0808e-132">0x01400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-133">n°2</span><span class="sxs-lookup"><span data-stu-id="0808e-133">2</span></span></p></td>
<td><p><span data-ttu-id="0808e-134">SN</span><span class="sxs-lookup"><span data-stu-id="0808e-134">Sn</span></span></p></td>
<td><p><span data-ttu-id="0808e-135">0x02400000</span><span class="sxs-lookup"><span data-stu-id="0808e-135">0x02400000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-136">3</span><span class="sxs-lookup"><span data-stu-id="0808e-136">3</span></span></p></td>
<td><p><span data-ttu-id="0808e-137">displayName</span><span class="sxs-lookup"><span data-stu-id="0808e-137">displayName</span></span></p></td>
<td><p><span data-ttu-id="0808e-138">0x03420000</span><span class="sxs-lookup"><span data-stu-id="0808e-138">0x03420000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-139">4 </span><span class="sxs-lookup"><span data-stu-id="0808e-139">4</span></span></p></td>
<td><p><span data-ttu-id="0808e-140">Titre</span><span class="sxs-lookup"><span data-stu-id="0808e-140">Title</span></span></p></td>
<td><p><span data-ttu-id="0808e-141">0x04000000</span><span class="sxs-lookup"><span data-stu-id="0808e-141">0x04000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-142">5 </span><span class="sxs-lookup"><span data-stu-id="0808e-142">5</span></span></p></td>
<td><p><span data-ttu-id="0808e-143">mailNickname</span><span class="sxs-lookup"><span data-stu-id="0808e-143">mailNickname</span></span></p></td>
<td><p><span data-ttu-id="0808e-144">0x05400000</span><span class="sxs-lookup"><span data-stu-id="0808e-144">0x05400000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-145">6 </span><span class="sxs-lookup"><span data-stu-id="0808e-145">6</span></span></p></td>
<td><p><span data-ttu-id="0808e-146">Company</span><span class="sxs-lookup"><span data-stu-id="0808e-146">Company</span></span></p></td>
<td><p><span data-ttu-id="0808e-147">0x06000000</span><span class="sxs-lookup"><span data-stu-id="0808e-147">0x06000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-148">7 </span><span class="sxs-lookup"><span data-stu-id="0808e-148">7</span></span></p></td>
<td><p><span data-ttu-id="0808e-149">physicalDeliveryOfficeName</span><span class="sxs-lookup"><span data-stu-id="0808e-149">physicalDeliveryOfficeName</span></span></p></td>
<td><p><span data-ttu-id="0808e-150">0x07000000</span><span class="sxs-lookup"><span data-stu-id="0808e-150">0x07000000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-151">8 </span><span class="sxs-lookup"><span data-stu-id="0808e-151">8</span></span></p></td>
<td><p><span data-ttu-id="0808e-152">msRTCSIP-PrimaryUserAddress</span><span class="sxs-lookup"><span data-stu-id="0808e-152">msRTCSIP-PrimaryUserAddress</span></span></p></td>
<td><p><span data-ttu-id="0808e-153">0x08520C00</span><span class="sxs-lookup"><span data-stu-id="0808e-153">0x08520C00</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-154">9 </span><span class="sxs-lookup"><span data-stu-id="0808e-154">9</span></span></p></td>
<td><p><span data-ttu-id="0808e-155">telephoneNumber</span><span class="sxs-lookup"><span data-stu-id="0808e-155">telephoneNumber</span></span></p></td>
<td><p><span data-ttu-id="0808e-156">0x09022800</span><span class="sxs-lookup"><span data-stu-id="0808e-156">0x09022800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-157">10 </span><span class="sxs-lookup"><span data-stu-id="0808e-157">10</span></span></p></td>
<td><p><span data-ttu-id="0808e-158">homePhone</span><span class="sxs-lookup"><span data-stu-id="0808e-158">homePhone</span></span></p></td>
<td><p><span data-ttu-id="0808e-159">0x0A302800</span><span class="sxs-lookup"><span data-stu-id="0808e-159">0x0A302800</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-160">11 </span><span class="sxs-lookup"><span data-stu-id="0808e-160">11</span></span></p></td>
<td><p><span data-ttu-id="0808e-161">Mobile</span><span class="sxs-lookup"><span data-stu-id="0808e-161">Mobile</span></span></p></td>
<td><p><span data-ttu-id="0808e-162">0x0B622800</span><span class="sxs-lookup"><span data-stu-id="0808e-162">0x0B622800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-163">12</span><span class="sxs-lookup"><span data-stu-id="0808e-163">12</span></span></p></td>
<td><p><span data-ttu-id="0808e-164">otherTelephone</span><span class="sxs-lookup"><span data-stu-id="0808e-164">otherTelephone</span></span></p></td>
<td><p><span data-ttu-id="0808e-165">0x0C302000</span><span class="sxs-lookup"><span data-stu-id="0808e-165">0x0C302000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-166">13 </span><span class="sxs-lookup"><span data-stu-id="0808e-166">13</span></span></p></td>
<td><p><span data-ttu-id="0808e-167">ipPhone</span><span class="sxs-lookup"><span data-stu-id="0808e-167">ipPhone</span></span></p></td>
<td><p><span data-ttu-id="0808e-168">0x0D302000</span><span class="sxs-lookup"><span data-stu-id="0808e-168">0x0D302000</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-169">14 </span><span class="sxs-lookup"><span data-stu-id="0808e-169">14</span></span></p></td>
<td><p><span data-ttu-id="0808e-170">Courrier</span><span class="sxs-lookup"><span data-stu-id="0808e-170">Mail</span></span></p></td>
<td><p><span data-ttu-id="0808e-171">0x0E500000</span><span class="sxs-lookup"><span data-stu-id="0808e-171">0x0E500000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-172">15 </span><span class="sxs-lookup"><span data-stu-id="0808e-172">15</span></span></p></td>
<td><p><span data-ttu-id="0808e-173">groupType</span><span class="sxs-lookup"><span data-stu-id="0808e-173">groupType</span></span></p></td>
<td><p><span data-ttu-id="0808e-174">0x0F010800</span><span class="sxs-lookup"><span data-stu-id="0808e-174">0x0F010800</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-175">16 </span><span class="sxs-lookup"><span data-stu-id="0808e-175">16</span></span></p></td>
<td><p><span data-ttu-id="0808e-176">Service</span><span class="sxs-lookup"><span data-stu-id="0808e-176">Department</span></span></p></td>
<td><p><span data-ttu-id="0808e-177">0x10000000</span><span class="sxs-lookup"><span data-stu-id="0808e-177">0x10000000</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-178">17 </span><span class="sxs-lookup"><span data-stu-id="0808e-178">17</span></span></p></td>
<td><p><span data-ttu-id="0808e-179">Description</span><span class="sxs-lookup"><span data-stu-id="0808e-179">Description</span></span></p></td>
<td><p><span data-ttu-id="0808e-180">0x11000100</span><span class="sxs-lookup"><span data-stu-id="0808e-180">0x11000100</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-181">18 </span><span class="sxs-lookup"><span data-stu-id="0808e-181">18</span></span></p></td>
<td><p><span data-ttu-id="0808e-182">Responsable</span><span class="sxs-lookup"><span data-stu-id="0808e-182">Manager</span></span></p></td>
<td><p><span data-ttu-id="0808e-183">0x12040001</span><span class="sxs-lookup"><span data-stu-id="0808e-183">0x12040001</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-184">neuf</span><span class="sxs-lookup"><span data-stu-id="0808e-184">19</span></span></p></td>
<td><p><span data-ttu-id="0808e-185">proxyAddress</span><span class="sxs-lookup"><span data-stu-id="0808e-185">proxyAddress</span></span></p></td>
<td><p><span data-ttu-id="0808e-186">0x00500105</span><span class="sxs-lookup"><span data-stu-id="0808e-186">0x00500105</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-187">vingtaine</span><span class="sxs-lookup"><span data-stu-id="0808e-187">20</span></span></p></td>
<td><p><span data-ttu-id="0808e-188">msExchHideFromAddressLists</span><span class="sxs-lookup"><span data-stu-id="0808e-188">msExchHideFromAddressLists</span></span></p></td>
<td><p><span data-ttu-id="0808e-189">0xFF000003</span><span class="sxs-lookup"><span data-stu-id="0808e-189">0xFF000003</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-190">99</span><span class="sxs-lookup"><span data-stu-id="0808e-190">99</span></span></p></td>
<td><p><span data-ttu-id="0808e-191">Entrée</span><span class="sxs-lookup"><span data-stu-id="0808e-191">entryID</span></span></p></td>
<td><p><span data-ttu-id="0808e-192">0x99000000</span><span class="sxs-lookup"><span data-stu-id="0808e-192">0x99000000</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0808e-193">Les numéros dans la colonne **ID** doivent être uniques et ne jamais être réutilisés.</span><span class="sxs-lookup"><span data-stu-id="0808e-193">The numbers in the **ID** column must be unique and should never be reused.</span></span> <span data-ttu-id="0808e-194">Le fait de garder des valeurs d’ID inférieures à 256 permet également d’économiser de l’espace dans les fichiers de sortie créés par le serveur de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="0808e-194">Also, keeping the ID values under 256 saves space in the output files written by the Address Book Server.</span></span> <span data-ttu-id="0808e-195">Toutefois, la valeur d’ID maximale est de 65 535.</span><span class="sxs-lookup"><span data-stu-id="0808e-195">However, the maximum ID value is 65535.</span></span> <span data-ttu-id="0808e-196">La colonne **nom** correspond au nom de l’attribut Active Directory que le réplicateur d’utilisateurs doit insérer dans la table AbUserEntry pour chaque contact.</span><span class="sxs-lookup"><span data-stu-id="0808e-196">The **Name** column corresponds to the Active Directory attribute name that User Replicator should put in the AbUserEntry table for each contact.</span></span> <span data-ttu-id="0808e-197">La valeur dans la colonne **Indicateurs** sert à définir le type d’attribut.</span><span class="sxs-lookup"><span data-stu-id="0808e-197">The value in the **Flags** column is used to define the type of attribute.</span></span> <span data-ttu-id="0808e-198">Les types d’attributs de serveur de carnet d’adresses suivants sont reconnus par le réplicateur d’utilisateurs, indiqué par l’octet bas de la valeur dans la colonne **Indicateurs**.</span><span class="sxs-lookup"><span data-stu-id="0808e-198">The following types of Address Book Server attributes are recognized by User Replicator, indicated by the low byte of the value in the **Flags** column.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0808e-199">Attribut</span><span class="sxs-lookup"><span data-stu-id="0808e-199">Attribute</span></span></th>
<th><span data-ttu-id="0808e-200">Description</span><span class="sxs-lookup"><span data-stu-id="0808e-200">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0808e-201">0x0</span><span class="sxs-lookup"><span data-stu-id="0808e-201">0x0</span></span></p></td>
<td><p><span data-ttu-id="0808e-p108">Attribut de chaîne. Le réplicateur d’utilisateurs convertit ce type en UTF-8 avant de le stocker dans la table AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="0808e-p108">A string attribute. User Replicator converts this type to UTF-8 before storing it in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-204">0x1</span><span class="sxs-lookup"><span data-stu-id="0808e-204">0x1</span></span></p></td>
<td><p><span data-ttu-id="0808e-p109">Attribut binaire. Le réplicateur d’utilisateurs stocke cet attribut dans le blob sans aucune conversion.</span><span class="sxs-lookup"><span data-stu-id="0808e-p109">A binary attribute. User Replicator stores this in the blob without any conversion.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-207">0x2</span><span class="sxs-lookup"><span data-stu-id="0808e-207">0x2</span></span></p></td>
<td><p><span data-ttu-id="0808e-208">Un attribut de chaîne, mais est inclus uniquement si la valeur d’attribut &quot;commence par&quot;tel :.</span><span class="sxs-lookup"><span data-stu-id="0808e-208">A string attribute, but is included only if the attribute value begins with &quot;tel:&quot;.</span></span> <span data-ttu-id="0808e-209">Ceci est principalement destiné aux attributs de chaînes à valeurs multiples, notamment <strong>proxyAddresses</strong>.</span><span class="sxs-lookup"><span data-stu-id="0808e-209">This is primarily for multi-valued string attributes, specifically <strong>proxyAddresses</strong>.</span></span> <span data-ttu-id="0808e-210">Dans ce cas, le serveur de carnet d’adresses est <strong></strong> uniquement intéressé par les entrées &quot;proxyAddresses qui&quot;commencent par Tél :.</span><span class="sxs-lookup"><span data-stu-id="0808e-210">In this case, Address Book Server is interested only in <strong>proxyAddresses</strong> entries that begin with &quot;tel:&quot;.</span></span> <span data-ttu-id="0808e-211">Par conséquent, dans l’intérêt d’économiser de l’espace, le réplicateur d’utilisateurs stocke &quot;uniquement les&quot;entrées qui commencent par Tél :.</span><span class="sxs-lookup"><span data-stu-id="0808e-211">Therefore, in the interest of saving space, User Replicator stores only the entries that begin with &quot;tel:&quot;.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-212">0x3</span><span class="sxs-lookup"><span data-stu-id="0808e-212">0x3</span></span></p></td>
<td><p><span data-ttu-id="0808e-p111">Attribut de chaîne booléen qui, s’il a la valeur VRAI, empêche au réplicateur d’utilisateurs d’inclure ce contact dans la table AbUserEntry. Si sa valeur est FAUX, cela empêche le réplicateur d’utilisateurs d’inclure les attributs de ce contact dans la table AbUserEntry, mais pas l’attribut spécifique comportant cet indicateur. Il s’agit d’un autre cas spécifique qui concerne principalement l’attribut <strong>msExchHideFromAddressLists</strong>.</span><span class="sxs-lookup"><span data-stu-id="0808e-p111">A Boolean string attribute, which if TRUE causes User Replicator to not include this contact in the AbUserEntry table. If FALSE, it causes User Replicator to include the attributes for this contact in the AbUserEntry table, but not the particular attribute with this flag. This is another special case type that is primarily for the <strong>msExchHideFromAddressLists</strong> attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-216">0x4</span><span class="sxs-lookup"><span data-stu-id="0808e-216">0x4</span></span></p></td>
<td><p><span data-ttu-id="0808e-217">Un attribut de chaîne, mais est inclus uniquement si la valeur d’attribut &quot;commence par&quot; SMTP : et &quot; @ &quot; inclut le symbole.</span><span class="sxs-lookup"><span data-stu-id="0808e-217">A string attribute, but is included only if the attribute value begins with &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-218">0x5</span><span class="sxs-lookup"><span data-stu-id="0808e-218">0x5</span></span></p></td>
<td><p><span data-ttu-id="0808e-219">Un attribut de chaîne, mais est inclus uniquement si la valeur d’attribut commence &quot;par Tél&quot; : &quot;ou SMTP&quot; : et inclut &quot; @ &quot; le symbole.</span><span class="sxs-lookup"><span data-stu-id="0808e-219">A string attribute, but is included only if the attribute value begins with either &quot;tel:&quot; or &quot;smtp:&quot; and includes the &quot;@&quot; symbol.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-220">0x100</span><span class="sxs-lookup"><span data-stu-id="0808e-220">0x100</span></span></p></td>
<td><p><span data-ttu-id="0808e-221">S’il est défini, cet attribut à plusieurs valeurs peut apparaître plusieurs fois pour chaque contact.</span><span class="sxs-lookup"><span data-stu-id="0808e-221">If set, this is a multi-valued attribute that can appear more than once for each contact.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-222">0x400</span><span class="sxs-lookup"><span data-stu-id="0808e-222">0x400</span></span></p></td>
<td><p><span data-ttu-id="0808e-p112">S’il est défini, cela permet d’identifier l’attribut du nom du compte d’utilisateur de messagerie pour un contact. Le serveur de carnet d’adresses utilise cet indicateur pour identifier la valeur d’attribut à afficher dans l’entrée du journal des événements de normalisation téléphonique.</span><span class="sxs-lookup"><span data-stu-id="0808e-p112">If set, this identifies the email user account name attribute for a contact. Address Book Server uses this flag to identify which attribute value to show in the phone normalization event log entry.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-225">0x800</span><span class="sxs-lookup"><span data-stu-id="0808e-225">0x800</span></span></p></td>
<td><p><span data-ttu-id="0808e-p113">S’il est défini, cela permet d’identifier un attribut requis pour un contact. Le serveur de carnet d’adresses ajoute un utilisateur dans la table AbUserEntry seulement si une valeur existe pour cet attribut dans Active Directory. S’il existe plusieurs attributs requis, seul l’un d’entre eux est nécessaire pour disposer d’une valeur afin d’inclure l’utilisateur dans la table AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="0808e-p113">If set, this identifies a required attribute for a contact. Address Book Server includes a user in the AbUserEntry table only if there is a value for this attribute in Active Directory. If there is more than one required attribute, only one of them is required to have a value to include the user in the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-229">0x1000</span><span class="sxs-lookup"><span data-stu-id="0808e-229">0x1000</span></span></p></td>
<td><p><span data-ttu-id="0808e-230">S’il est défini, le serveur de carnet d’adresses normalise toujours la valeur de cet attribut.</span><span class="sxs-lookup"><span data-stu-id="0808e-230">If set, Address Book Server always normalizes the value of this attribute.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-231">0 x 2000</span><span class="sxs-lookup"><span data-stu-id="0808e-231">0x2000</span></span></p></td>
<td><p><span data-ttu-id="0808e-232">S’il est défini, le serveur de carnet d’adresses utilise le numéro normalisé des <strong>adresses proxy</strong>, si le paramètre CMS <strong>UseNormalizationRules</strong> a la valeur FAUX, sinon il se comporte comme si le bit d’indicateur était 0x1000.</span><span class="sxs-lookup"><span data-stu-id="0808e-232">If set, Address Book Server uses the normalized number from <strong>proxyAddresses</strong>, if the <strong>UseNormalizationRules</strong> CMS setting is FALSE; otherwise it behaves the same as when the flag bit is 0x1000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-233">0x4000</span><span class="sxs-lookup"><span data-stu-id="0808e-233">0x4000</span></span></p></td>
<td><p><span data-ttu-id="0808e-p114">S’il est défini, le serveur de carnet d’adresses n’inclut pas d’objets dans la table AbUserEntry qui contiennent cette valeur pour l’attribut spécifié. Par exemple, si l’attribut <strong>msRTCSIP-PrimaryUserAddress</strong> a ce bit d’indicateur défini, les contacts disposant de cet attribut ne sont alors pas créés sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="0808e-p114">If set, Address Book Server does not include objects in the AbUserEntry table that have this value for the specified attribute. For example, if the <strong>msRTCSIP-PrimaryUserAddress</strong> attribute has this flag bit set, then contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-236">0x8000</span><span class="sxs-lookup"><span data-stu-id="0808e-236">0x8000</span></span></p></td>
<td><p><span data-ttu-id="0808e-p115">S’il est défini, le serveur de carnet d’adresses n’inclut pas d’objets dans la table AbUserEntry qui ne contiennent pas cette valeur pour l’attribut spécifié. Si les deux bits d’indicateur 0x4000 et 0x8000 sont définis sur un objet, l’attribut avec la valeur de bit d’indicateur définie sur 0x4000 est prioritaire et l’objet est exclu de la table AbUserEntry.</span><span class="sxs-lookup"><span data-stu-id="0808e-p115">If set, Address Book Server does not include objects in the AbUserEntry table that do not have this value for the specified attribute. If both the 0x4000 and 0x8000 flag bits are set on an object, the attribute with the flag bit value set to 0x4000 takes precedence, and the object is excluded from the AbUserEntry table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-239">0x10000</span><span class="sxs-lookup"><span data-stu-id="0808e-239">0x10000</span></span></p></td>
<td><p><span data-ttu-id="0808e-p116">Représente un objet de groupe s’il est défini. Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour inclure les contacts avec l’attribut <strong>groupType</strong> dont la présence indique un groupe (par exemple, une liste de distribution ou un groupe de sécurité).</span><span class="sxs-lookup"><span data-stu-id="0808e-p116">If set, this represents a group object. User Replicator uses this flag bit to include contacts with the <strong>groupType</strong> attribute whose presence indicates a group (for example, a distribution list or security group).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-242">0x20000</span><span class="sxs-lookup"><span data-stu-id="0808e-242">0x20000</span></span></p></td>
<td><p><span data-ttu-id="0808e-243">S’il est défini, le réplicateur d’utilisateurs utilise ce bit d’indicateur pour inclure cet attribut dans les fichiers du serveur de carnet d’adresses propres au périphérique (c’est-à-dire les fichiers avec l’extension .dabs).</span><span class="sxs-lookup"><span data-stu-id="0808e-243">If set, User Replicator uses this flag bit to include this attribute in device-specific Address Book Server files (that is, files with a .dabs extension).</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0808e-244">Dans les versions précédentes de Lync Server, lors de l’application d’une modification à Active Directory, l’administrateur devait exécuter les applets de commande **Update-CSUserDatabase** et **Update – CSAddressBook** Windows PowerShell pour conserver immédiatement la modification apportée à la base de données utilisateur Lync Server et à la base de données RTCab.</span><span class="sxs-lookup"><span data-stu-id="0808e-244">In previous versions of Lync Server, when applying a change to Active Directory, the administrator would be required to run **Update -CSUserDatabase** and **Update –CSAddressBook** Windows PowerShell cmdlets to persist the change to the Lync Server user database and RTCab database immediately.</span></span> <span data-ttu-id="0808e-245">Dans Lync Server 2013, le réplicateur d’utilisateurs Lync Server récupère les modifications à partir d’Active Directory et met à jour la base de données utilisateur Lync Server en fonction d’un intervalle configuré.</span><span class="sxs-lookup"><span data-stu-id="0808e-245">In Lync Server 2013, Lync Server User Replicator will pick up the changes from Active Directory and update the Lync Server user database based on a configured interval.</span></span> <span data-ttu-id="0808e-246">Lync Server User Replicator propagera également les modifications à la base de données RTCab rapidement, sans que l’administrateur doive exécuter Update-CSAddressBook.</span><span class="sxs-lookup"><span data-stu-id="0808e-246">Lync Server User Replicator will also propagate the changes to the RTCab database quickly without the administrator having to run Update-CSAddressBook.</span></span> <span data-ttu-id="0808e-247">Si la requête Web du carnet d’adresses est activée, les modifications seront reflétées dans les résultats de la recherche par les clients Lync.</span><span class="sxs-lookup"><span data-stu-id="0808e-247">If Address Book Web query is enabled, then the changes will be reflected in search results by Lync clients.</span></span> <span data-ttu-id="0808e-248">Les administrateurs devront seulement exécuter Update-CSAddressBook si le téléchargement du fichier de carnet d’adresses est activé.</span><span class="sxs-lookup"><span data-stu-id="0808e-248">Administrators will only need to run Update -CSAddressBook if the Address Book file download is enabled.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0808e-249">Par défaut, Lync Server User Replicator s’exécute automatiquement toutes les 5 minutes.</span><span class="sxs-lookup"><span data-stu-id="0808e-249">By default Lync Server User Replicator runs automatically every 5 minutes.</span></span> <span data-ttu-id="0808e-250">Vous pouvez configurer cet intervalle à l’aide de Set-CSUserReplicatorConfiguration &lt; &gt;-ReplicationCycleInterval.</span><span class="sxs-lookup"><span data-stu-id="0808e-250">You can configure this interval by using Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.</span></span>



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a><span data-ttu-id="0808e-251">Filtrage du carnet d’adresses</span><span class="sxs-lookup"><span data-stu-id="0808e-251">Filtering the Address Book</span></span>

<span data-ttu-id="0808e-252">Les utilisateurs renseignés dans les fichiers du carnet d’adresses peuvent être contrôlés en fonction de certains attributs des services de domaine Active Directory figurant dans la table AbAttribute.</span><span class="sxs-lookup"><span data-stu-id="0808e-252">The users populated in the Address Book Server files can be controlled based on certain Active Directory Domain Services attributes listed in the AbAttribute table.</span></span> <span data-ttu-id="0808e-253">Parmi les attributs utilisés pour le filtrage figure l’attribut **msExchangeHideFromAddressBook**.</span><span class="sxs-lookup"><span data-stu-id="0808e-253">One such attribute used for filtering is the **msExchangeHideFromAddressBook** attribute.</span></span> <span data-ttu-id="0808e-254">Il s’agit d’un attribut utilisateur ajouté par le schéma Exchange.</span><span class="sxs-lookup"><span data-stu-id="0808e-254">This is a user attribute added by the Exchange schema.</span></span> <span data-ttu-id="0808e-255">Si la valeur de cet attribut est VRAI, le serveur Exchange Server utilise cet attribut pour masquer le contact dans la liste d’adresses globale d’Outlook.</span><span class="sxs-lookup"><span data-stu-id="0808e-255">If the value of this attribute is TRUE, Exchange Server uses this attribute to hide the contact from the Outlook Global Address List (GAL).</span></span> <span data-ttu-id="0808e-256">De même, si la valeur de cet attribut est VRAI, le réplicateur d’utilisateurs n’inclut pas cet utilisateur dans la table AbUserEntry qui sera également absent des fichiers du serveur de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="0808e-256">Similarly, if the value of this attribute is TRUE, User Replicator does not include that user in the AbUserEntry table and this user will not be in the Address Book Server files.</span></span>

<span data-ttu-id="0808e-p120">Vous pouvez utiliser certains bits d’indicateur pour définir un filtre à utiliser sur les attributs du serveur de carnet d’adresses. Par exemple, la présence de certains bits d’indicateurs peut identifier un attribut comme étant un attribut à inclure ou à exclure. Le réplicateur d’utilisateurs filtre les contacts contenant un attribut à exclure et ceux ne contenant pas d’attribut à inclure.</span><span class="sxs-lookup"><span data-stu-id="0808e-p120">You can use some flag bits to define a filter to use on Address Book Server attributes. For example, the presence of certain flag bits can identify an attribute as an include attribute or an exclude attribute. User Replicator filters out contacts that contain an exclude attribute and filters out contains that do not contain an include attribute.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0808e-260">Pour plus d’informations sur le filtrage du carnet d’adresses, voir <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">cmdlets du serveur de carnet d’adresses dans Lync Server 2013</A>et <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filtrer Lync 2013 d’adresses</A></span><span class="sxs-lookup"><span data-stu-id="0808e-260">For more information about filtering the Address Book, see <A href="https://technet.microsoft.com/library/gg415643(v=ocs.15)">Address Book Server cmdlets in Lync Server 2013</A>, and <A href="http://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</A></span></span>



</div>

<span data-ttu-id="0808e-p121">Il existe actuellement trois filtres différents. Le tableau suivant les répertorie.</span><span class="sxs-lookup"><span data-stu-id="0808e-p121">Currently, there are three different filters. The following table lists these filters.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0808e-263">Attribut</span><span class="sxs-lookup"><span data-stu-id="0808e-263">Attribute</span></span></th>
<th><span data-ttu-id="0808e-264">Description</span><span class="sxs-lookup"><span data-stu-id="0808e-264">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0808e-265">0x800</span><span class="sxs-lookup"><span data-stu-id="0808e-265">0x800</span></span></p></td>
<td><p><span data-ttu-id="0808e-p122">S’il est défini, cela permet d’identifier un attribut requis pour un contact. Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour filtrer les contacts qui ne contiennent pas au moins un attribut obligatoire. OuPathId est un attribut obligatoire qui est toujours défini. Au moins un des autres attributs obligatoires doit donc être défini. Sinon, le contact (c’est-à-dire avec la valeur de l’attribut obligatoire OuPathId) ne sera toujours pas ajouté à la base de données. Par exemple, si <strong>telephoneNumber</strong> et <strong>homePhone</strong> sont définis comme attributs obligatoires, seuls les contacts contenant au moins un de ces attributs sont ajoutés à la base de données.</span><span class="sxs-lookup"><span data-stu-id="0808e-p122">If set, this identifies a required attribute for a contact. User Replicator uses this flag bit to filter out contacts that do not contain at least one required attribute. The OuPathId is a required attribute, which is always set. So at least one of other required attributes should be set. Otherwise, contact (that is, with value of required attribute OuPathId) will still not be written to database. For example, if <strong>telephoneNumber</strong> and <strong>homePhone</strong> are defined as required attributes, only the contacts that have at least one of these attributes are written to the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0808e-272">0x4000</span><span class="sxs-lookup"><span data-stu-id="0808e-272">0x4000</span></span></p></td>
<td><p><span data-ttu-id="0808e-p123">Identifie un attribut à exclure s’il est défini. Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour filtrer les contacts qui contiennent cet attribut. Par exemple, si <strong>msRTCSIP-PrimaryUserAddress</strong> est défini en tant qu’attribut à exclure, les contacts disposant de cet attribut ne sont pas créés sur la base de données.</span><span class="sxs-lookup"><span data-stu-id="0808e-p123">If set, this identifies an exclude attribute. User Replicator uses this flag bit to filter out contacts that contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an exclude attribute, contacts that have this attribute are not written to the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0808e-276">0x8000</span><span class="sxs-lookup"><span data-stu-id="0808e-276">0x8000</span></span></p></td>
<td><p><span data-ttu-id="0808e-p124">Identifie un attribut à inclure s’il est défini. Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour filtrer les contacts qui ne contiennent pas cet attribut. Par exemple, si <strong>msRTCSIP-PrimaryUserAddress</strong> est défini en tant qu’attribut à inclure, les contacts disposant de cet attribut sont ajoutés à la base de données.</span><span class="sxs-lookup"><span data-stu-id="0808e-p124">If set, this identifies an include attribute. User Replicator uses this flag bit to filter out contacts that do not contain this attribute. For example, if <strong>msRTCSIP-PrimaryUserAddress</strong> is defined as an include attribute, only the contacts that have this attribute are written to the database.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="0808e-280">Si les deux bits d’indicateur 0x4000 (attribut à exclure) et 0x8000 (attribut à inclure) sont définis, le bit 0x4000 remplace le bit 0x8000 et le contact est exclu.</span><span class="sxs-lookup"><span data-stu-id="0808e-280">If both the 0x4000 (exclude attribute) and 0x8000 (include attribute) flag bits are set, the 0x4000 bit overrides the 0x8000 bit and the contact is excluded.</span></span>



</div>

<span data-ttu-id="0808e-p125">Même si vous pouvez filtrer le carnet d’adresses afin de n’inclure que certains utilisateurs, la limitation des entrées n’empêche pas les autres utilisateurs de contacter les utilisateurs filtrés ou d’afficher leur statut de présence. Les utilisateurs peuvent toujours rechercher, envoyer des messages instantanés ou initier manuellement des appels pour les utilisateurs absents du carnet d’adresses en entrant le nom de connexion complet d’un utilisateur. Les informations de contact d’un utilisateur peuvent également être trouvées dans Outlook.</span><span class="sxs-lookup"><span data-stu-id="0808e-p125">Although you can filter the Address Book to include only certain users, limiting entries does not limit other users' ability to contact the filtered users or to see their presence status. Users can always find, manually send instant messages, or manually initiate calls to users not in the Address Book by entering a user's complete sign-in name. Also, contact information for a user could also be found in Outlook.</span></span>

<span data-ttu-id="0808e-284">Bien qu’il soit possible d’utiliser des enregistrements de contacts complets dans les fichiers de carnet d’adresses, vous pouvez utiliser Lync Server pour lancer des appels vocaux de messagerie, téléphoniques ou d’entreprise (c’est-à-dire, si voix entreprise est activé sur le serveur) avec des utilisateurs qui ne sont pas configurés pour l’initiation de session. Protocol (SIP), certaines organisations préfèrent inclure uniquement les utilisateurs à extension SIP dans leurs entrées de serveur de carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="0808e-284">While having full contact records in the Address Book files enables you to use Lync Server to initiate email, telephone, or Enterprise Voice calls (that is, if Enterprise Voice is enabled on the server) with users that are not configured for Session Initiation Protocol (SIP), some organizations prefer to include only SIP-enabled users in their Address Book Server entries.</span></span> <span data-ttu-id="0808e-285">Vous pouvez filtrer le carnet d’adresses de manière à inclure uniquement les utilisateurs activés pour SIP en effaçant le bit 0x800 dans la colonne **Indicateurs** des attributs obligatoires suivants : **mailNickname**, **telephoneNumber**, **homePhone** et **mobile**.</span><span class="sxs-lookup"><span data-stu-id="0808e-285">You can filter the Address Book to include only SIP-enabled users by clearing the 0x800 bit in the **Flags** column of the following required attributes: **mailNickname**, **telephoneNumber**, **homePhone**, and **mobile**.</span></span> <span data-ttu-id="0808e-286">Vous pouvez également filtrer le carnet d’adresses de manière à inclure uniquement les utilisateurs activés pour SIP en définissant le bit 0x8000 (attribut à inclure) dans la colonne **Indicateurs** de l’attribut **msRTCSIP-PrimaryUserAddress**.</span><span class="sxs-lookup"><span data-stu-id="0808e-286">You can also filter the Address Book to include only SIP-enabled users by setting the 0x8000 (include attribute) in the **Flags** column of the **msRTCSIP-PrimaryUserAddress** attribute.</span></span> <span data-ttu-id="0808e-287">Cela permet également d’exclure les comptes de service des fichiers du carnet d’adresses.</span><span class="sxs-lookup"><span data-stu-id="0808e-287">This also helps to exclude service accounts from the Address Book files.</span></span>

<span data-ttu-id="0808e-288">Après avoir modifié la table AbAttribute, vous pouvez actualiser les données de la table AbUserEntry en exécutant la commande de l’applet de commande **Update-CsUserDatabase**.</span><span class="sxs-lookup"><span data-stu-id="0808e-288">After you modify the AbAttribute table, you can refresh the data in the AbUserEntry table by running the cmdlet **Update-CsUserDatabase** command.</span></span> <span data-ttu-id="0808e-289">Une fois que la réplication du réplicateur d’utilisateurs est terminée, vous pouvez mettre à jour le fichier dans le magasin de fichiers du serveur de carnet d’adresses en exécutant manuellement la commande de l’applet de commande **UpdateCsAddressBook**.</span><span class="sxs-lookup"><span data-stu-id="0808e-289">After UR replication completes, you can update the file in the Address Book Server file store by manually running the cmdlet **UpdateCsAddressBook** command.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0808e-290">Le serveur frontal sur lequel le serveur de carnet d’adresses est placé n’est pas configurable de manière administrative.</span><span class="sxs-lookup"><span data-stu-id="0808e-290">The Front End Server that the Address Book Server is placed is not administratively configurable.</span></span> <span data-ttu-id="0808e-291">L’un d’entre eux est choisi pendant le déploiement, généralement, le premier serveur frontal déployé.</span><span class="sxs-lookup"><span data-stu-id="0808e-291">One is chosen during deployment—typically, the first Front End Server deployed.</span></span> <span data-ttu-id="0808e-292">En cas de défaillance, le service de carnet d’adresses se déplace vers un autre serveur frontal et ne requiert aucune attention administrative.</span><span class="sxs-lookup"><span data-stu-id="0808e-292">In the event of failure, the Address Book Service will move to another Front End Server, and requires no administrative attention.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0808e-293">Si vous avez consolidé ou modifié votre infrastructure à partir d’un déploiement à forêts multiples ou d’un déploiement parent/enfant (par exemple, en consolidant votre infrastructure avant de passer à Lync Server), vous pouvez constater que le téléchargement du service de carnet d’adresses et la requête Web du carnet d’adresses échouent pour certains utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="0808e-293">If you have consolidated or otherwise modified your infrastructure from a multi-forest deployment or a parent/child deployment (such as consolidating your infrastructure before moving to Lync Server), you may find that the Address Book service download and the Address Book Web Query fails for some users.</span></span> <span data-ttu-id="0808e-294">Lorsqu’il se trouve dans un déploiement comportant plusieurs domaines ou forêts, l’attribut <STRONG>MsRTCSIP-OriginatorSid</STRONG> est renseigné sur les objets utilisateur qui rencontrent ce problème.</span><span class="sxs-lookup"><span data-stu-id="0808e-294">When in a deployment that had multiple domains or forests, the attribute <STRONG>MsRTCSIP-OriginatorSid</STRONG> is populated on the user objects that are exhibiting the issue.</span></span> <span data-ttu-id="0808e-295">L’attribut <STRONG>MsRTCSIP-OriginatorSid</STRONG> doit être défini avec la valeur NULL sur ces objets pour résoudre le problème.</span><span class="sxs-lookup"><span data-stu-id="0808e-295">The <STRONG>MsRTCSIP-OriginatorSid</STRONG> attribute must be set to NULL on these objects to resolve the issue.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

