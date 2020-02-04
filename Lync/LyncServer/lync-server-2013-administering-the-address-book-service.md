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

# <a name="administering-the-address-book-service-in-lync-server-2013"></a>Administration du service de carnet d’adresses dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-02-05_

Dans le cadre du déploiement de Lync Server, Enterprise Edition ou Standard Edition Server, le service de carnet d’adresses est installé par défaut. La base de données utilisée par le service de carnet d’adresses (RTCab) est créée sur SQL Server (pour Enterprise Edition, il s’agit du serveur principal SQL Server ; pour Standard Edition Server, serveur SQL colocalisé).

<div>


> [!NOTE]  
> Pour plus d’informations sur l’utilisation de la <STRONG>modification ADSI</STRONG> pour modifier les attributs d’objet des services de domaine Active Directory, voir <A href="http://go.microsoft.com/fwlink/?linkid=330427">ADSI Edit</A>. Pour plus d’informations sur un outil du kit de ressources pour le service de carnet d’adresses, voir <A href="http://go.microsoft.com/fwlink/?linkid=330429">outils du kit de ressources Microsoft Lync Server 2013</A>.



</div>

<div>

## <a name="address-book-server-phone-number-normalization"></a>Normalisation des numéros de téléphone du serveur du carnet d’adresses

Lync Server nécessite des numéros de téléphone RFC 3966/E. 164 normalisés. Pour utiliser les numéros de téléphone non structurés ou structurés de manière incohérente, Lync Server s’appuie sur le serveur du carnet d’adresses pour prétraiter les numéros de téléphone avant d’être remis aux règles de normalisation. Lorsque vous utilisez un numéro de téléphone à partir du carnet d’adresses et que la règle de normalisation est appliquée, les clients, tels que Lync Phone Edition et Lync mobile, peuvent utiliser ces numéros normalisés.

Les règles de normalisation utilisées dans les versions précédentes risquent de ne pas fonctionner correctement sans quelques ajustements. Dans la mesure où les caractères blancs et non obligatoires sont supprimés avant les règles de normalisation, si votre expression Regex recherche plus précisément un tiret ou un autre caractère supprimé, votre règle de normalisation peut échouer. Nous vous conseillons de passer en revue les règles de normalisation pour vous assurer qu’elles ne recherchent pas ces caractères non obligatoires, ou que la règle peut échouer de manière harmonieuse et poursuivre en cas d’absence du caractère au niveau de la règle.

</div>

<div>

## <a name="user-replicator-and-address-book-server"></a>Serveur du carnet d’adresses et réplicateur d’utilisateurs

Le serveur du carnet d’adresses utilise les données fournies par le réplicateur d’utilisateurs pour mettre à jour les informations qu’il obtient initialement de la liste d’adresses globale. Le réplicateur d’utilisateurs écrit les attributs des services de domaine Active Directory pour chaque utilisateur, contact et groupe dans la table AbUserEntry de la base de données, et le serveur du carnet d’adresses synchronise les données utilisateur de la base de données dans les fichiers du magasin de fichiers du serveur de carnet d’adresses et dans la base de données du RTCab. Le schéma de la table AbUserEntry utilise deux colonnes, **UserGuid** et **UserData**. **UserGuid** est la colonne d’index et contient le GUID de 16 octets de l’objet Active Directory. **UserData** est une colonne d’image qui contient tous les attributs de services de domaine Active Directory (AD FS) déjà mentionnés pour ce contact.

Le réplicateur d’utilisateurs détermine les attributs Active Directory à écrire en lisant une table de configuration située dans la même instance SQL Server que la table AbUserEntry. La table AbAttribute contient trois colonnes, **ID**, **nom**, **indicateurs**et **activer**. La table est créée lors de la configuration de la base de données. Si la table AbAttribute est vide, le réplicateur d’utilisateurs ignore la logique de traitement de la table AbUserEntry. Les attributs de serveur du carnet d’adresses sont dynamiques et extraits de la table AbAttribute, qui est initialement rédigée par le serveur du carnet d’adresses lorsque le serveur du carnet d’adresses est activé.

L’activation du serveur du carnet d’adresses remplit la table AbAttribute avec les valeurs figurant dans le tableau suivant.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>ID</th>
<th>Nom</th>
<th>Indicateurs</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>givenName</p></td>
<td><p>0x01400000</p></td>
</tr>
<tr class="even">
<td><p>deuxième</p></td>
<td><p>Perso</p></td>
<td><p>0x02400000</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>displayName</p></td>
<td><p>0x03420000</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Titre</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>Elle</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>version8</p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>09</p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>0,10</p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>27,9</p></td>
<td><p>Mobile</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>midi</p></td>
<td><p>otherTelephone</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>n°13</p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>14</p></td>
<td><p>Fonctionnalité</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>0,15</p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>Seiz</p></td>
<td><p>Service</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>Play</p></td>
<td><p>Description</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>19</p></td>
<td><p>Responsable</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>19,6</p></td>
<td><p>proxyAddress</p></td>
<td><p>0x00500105</p></td>
</tr>
<tr class="even">
<td><p>CX3-20</p></td>
<td><p>msExchHideFromAddressLists</p></td>
<td><p>0xFF000003</p></td>
</tr>
<tr class="odd">
<td><p>99</p></td>
<td><p>Identificateur</p></td>
<td><p>0x99000000</p></td>
</tr>
</tbody>
</table>


Les nombres de la colonne **ID** doivent être uniques et ne doivent jamais être réutilisés. En outre, le fait de maintenir les valeurs d’identification sous 256 économise de l’espace dans les fichiers de sortie écrits par le serveur du carnet d’adresses. Toutefois, la valeur d’ID maximale est 65535. La colonne **Name** correspond au nom de l’attribut Active Directory que le réplicateur d’utilisateurs doit placer dans la table AbUserEntry de chaque contact. La valeur de la colonne **indicateurs** permet de définir le type d’attribut. Les types suivants de valeurs de serveur de carnet d’adresses sont reconnus par User Replicator, indiqués par le poids faible de la valeur dans la colonne **indicateurs** .


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x0</p></td>
<td><p>Un attribut de chaîne. Le réplicateur d’utilisateurs convertit ce type en UTF-8 avant de le stocker dans la table AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>Un attribut binaire. Le réplicateur d’utilisateurs enregistre cela dans l’objet BLOB sans conversion.</p></td>
</tr>
<tr class="odd">
<td><p>0X2</p></td>
<td><p>Un attribut de chaîne, mais est inclus uniquement si la valeur de l' &quot;attribut commence&quot;par tel :. Cela s’adresse principalement aux attributs de chaîne à valeurs multiples, en particulier <strong>proxyAddresses</strong>. Dans ce cas, le serveur du carnet d’adresses est <strong></strong> intéressé uniquement dans les entrées &quot;proxyAddresses qui&quot;commencent par la lettre « tel : ». Par conséquent, pour économiser de l’espace, le réplicateur d’utilisateurs stocke uniquement les entrées &quot;qui commencent&quot;par tel :.</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>Un attribut de chaîne booléenne, qui, si TRUE, le réplicateur de utilisateurs n’inclura pas ce contact dans la table AbUserEntry. Si la valeur est FALSe, le réplicateur d’utilisateurs doit inclure les attributs pour ce contact dans la table AbUserEntry, mais pas l’attribut particulier avec cet indicateur. Il s’agit d’un autre type de cas particulier qui est essentiellement destiné à l’attribut <strong>msExchHideFromAddressLists</strong> .</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>Un attribut de chaîne, mais est inclus uniquement si la valeur de l' &quot;attribut commence&quot; par SMTP : &quot; @ &quot; et inclut le symbole.</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>Un attribut de chaîne, mais est inclus uniquement si la valeur de l’attribut &quot;commence par&quot; tel &quot;: ou&quot; SMTP : et &quot; @ &quot; inclut le symbole.</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>S’il est défini, il s’agit d’un attribut à valeurs multiples qui peut apparaître plusieurs fois pour chaque contact.</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>Si cette valeur est définie, elle identifie l’attribut du nom de compte d’utilisateur de messagerie d’un contact. Le serveur du carnet d’adresses utilise cet indicateur pour identifier la valeur d’attribut à afficher dans l’entrée du journal des événements de normalisation du téléphone.</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>Si cette valeur est définie, elle identifie un attribut obligatoire pour un contact. Le serveur du carnet d’adresses inclut un utilisateur dans la table AbUserEntry uniquement s’il existe une valeur pour cet attribut dans Active Directory. S’il existe plusieurs attributs obligatoires, un seul d’eux est requis pour inclure une valeur dans la table AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x1000</p></td>
<td><p>S’il est défini, le serveur du carnet d’adresses normalise toujours la valeur de cet attribut.</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>S’il est défini, le serveur du carnet d’adresses utilise le numéro normalisé de <strong>proxyAddresses</strong>, si le paramètre <strong>UseNormalizationRules</strong> CMS a la valeur false. Sinon, il a le même comportement que lorsque le bit de l’indicateur est 0x1000.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>S’il est défini, le serveur du carnet d’adresses n’inclut pas les objets dans la table AbUserEntry qui ont cette valeur pour l’attribut spécifié. Par exemple, si l’attribut <strong>msRTCSIP-PrimaryUserAddress</strong> est défini pour ce bit d’indicateur, les contacts qui ont cet attribut ne sont pas écrits dans la base de données.</p></td>
</tr>
<tr class="odd">
<td><p>vert</p></td>
<td><p>S’il est défini, le serveur du carnet d’adresses n’inclut pas d’objets dans la table AbUserEntry qui n’ont pas cette valeur pour l’attribut spécifié. Si les bits d’indicateur 0x4000 et 0x8000 sont définis sur un objet, l’attribut avec la valeur de bit Flag définie sur 0x4000 a la priorité et l’objet est exclu de la table AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>S’il est défini, il s’agit d’un objet de groupe. Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour inclure les contacts avec l’attribut <strong>GroupType</strong> dont la présence indique un groupe (par exemple, une liste de distribution ou un groupe de sécurité).</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>S’il est défini, le réplicateur d’utilisateurs utilise ce bit d’indicateur pour inclure cet attribut dans les fichiers serveur du carnet d’adresses spécifiques à l’appareil (c’est-à-dire, les fichiers avec l’extension. dabs).</p></td>
</tr>
</tbody>
</table>


Dans les versions précédentes de Lync Server, lors de l’application d’une modification à Active Directory, l’administrateur est tenu d’exécuter **Update-CSUserDatabase** et **Update-CSAddressBook** des cmdlets Windows PowerShell pour persister la modification de la base de données utilisateur et de la base de données RTCab du serveur Lync. Dans Lync Server 2013, le réplicateur d’utilisateurs de Lync Server capte les modifications d’Active Directory et met à jour la base de données utilisateur de Lync Server en fonction d’un intervalle configuré. Le réplicateur d’utilisateurs de Lync Server propage également les modifications apportées à la base de données RTCab sans qu’il soit nécessaire d’exécuter Update-CSAddressBook. Si la requête Web du carnet d’adresses est activée, les modifications sont répercutées dans les résultats de recherche par les clients Lync. Les administrateurs devront uniquement exécuter Update-CSAddressBook si le téléchargement du fichier du carnet d’adresses est activé.

<div>


> [!NOTE]  
> Par défaut, le réplicateur d’utilisateurs de Lync Server s’exécute automatiquement toutes les cinq minutes. Vous pouvez configurer cet intervalle à l’aide de Set-CSUserReplicatorConfiguration &lt; &gt;-ReplicationCycleInterval.



</div>

</div>

<div>

## <a name="filtering-the-address-book"></a>Filtrage du carnet d’adresses

Les utilisateurs remplis dans les fichiers du serveur du carnet d’adresses peuvent être contrôlés en fonction de certains attributs de services de domaine Active Directory, répertoriés dans la table abattribut. Il s’agit de l’attribut **msExchangeHideFromAddressBook** utilisé pour le filtrage. Il s’agit d’un attribut utilisateur ajouté par le schéma Exchange. Si la valeur de cet attribut est TRUE, Exchange Server utilise cet attribut pour masquer le contact dans la liste d’adresses globale Outlook. De même, si la valeur de cet attribut est TRUE, le réplicateur d’utilisateurs n’inclut pas cet utilisateur dans la table AbUserEntry, et cet utilisateur ne se trouve pas dans les fichiers du serveur du carnet d’adresses.

Vous pouvez utiliser certains bits d’indicateur pour définir un filtre à utiliser sur les attributs du serveur du carnet d’adresses. Par exemple, la présence de certains bits d’indicateur peut identifier un attribut en tant qu’attribut include ou attribut exclude. Le réplicateur d’utilisateurs filtre les contacts qui contiennent un attribut exclude et filtres qui ne contiennent pas d’attribut include.

<div>


> [!WARNING]  
> Pour plus d’informations sur le filtrage du carnet d’adresses, voir <A href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">applets de filtre d’adresses serveur dans Lync Server 2013</A>et <A href="http://go.microsoft.com/fwlink/?linkid=330430">filtrer le carnet d’adresses Lync 2013</A>



</div>

Il existe actuellement trois filtres différents. Le tableau suivant répertorie ces filtres.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Attribut</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>Si cette valeur est définie, elle identifie un attribut obligatoire pour un contact. Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour filtrer les contacts qui ne contiennent pas au moins un attribut obligatoire. OuPathId est un attribut obligatoire, qui est toujours défini. Pour pouvoir définir au moins un des autres attributs obligatoires. Dans le cas contraire, le contact (c’est-à-dire, avec la valeur de l’attribut requis OuPathId) ne sera toujours pas écrit dans la base de données. Par exemple, si <strong>telephoneNumber</strong> et <strong>homePhone</strong> sont définis comme attributs obligatoires, seuls les contacts qui ont au moins un de ces attributs sont écrits dans la base de données.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Si cette valeur est définie, elle identifie un attribut exclude. Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour filtrer les contacts qui contiennent cet attribut. Par exemple, si <strong>msRTCSIP-PrimaryUserAddress</strong> est défini en tant qu’attribut exclude, les contacts qui ont cet attribut ne sont pas écrits dans la base de données.</p></td>
</tr>
<tr class="odd">
<td><p>vert</p></td>
<td><p>Si cette valeur est définie, elle identifie un attribut include. Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour filtrer les contacts qui ne contiennent pas cet attribut. Par exemple, si <strong>msRTCSIP-PrimaryUserAddress</strong> est défini comme attribut include, seuls les contacts dotés de cet attribut sont écrits dans la base de données.</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Si les bits d’indicateur 0x4000 (Exclude) et 0x8000 (include Attribute) sont définis, le bit 0x4000 remplace le bit 0x8000 et le contact est exclu.



</div>

Même si vous pouvez filtrer le carnet d’adresses pour inclure uniquement certains utilisateurs, le fait de limiter les entrées ne limite pas la capacité des utilisateurs à contacter les utilisateurs filtrés ou à voir leur statut de présence. Les utilisateurs peuvent toujours retrouver, envoyer des messages instantanés manuellement ou lancer manuellement des appels vers des utilisateurs qui ne se trouvent pas dans le carnet d’adresses en entrant le nom de connexion complet d’un utilisateur. Vous pouvez également consulter les informations de contact d’un utilisateur dans Outlook.

Lorsque vous avez des enregistrements de contact complets dans les fichiers du carnet d’adresses vous permet d’utiliser Lync Server pour lancer le courrier électronique, le téléphone ou les appels vocaux d’entreprise (autrement dit, si Enterprise Voice est activé sur le serveur) avec des utilisateurs qui ne sont pas configurés pour le lancement de la session Protocole (SIP), certaines organisations préfèrent inclure uniquement les utilisateurs compatibles SIP dans les entrées du serveur du carnet d’adresses. Vous pouvez filtrer le carnet d’adresses pour inclure uniquement les utilisateurs compatibles SIP en effaçant le bit de 0x800 dans la colonne **indicateurs** des attributs obligatoires suivants : **mailnickname**, **telephoneNumber**, **homePhone**et **mobile**. Vous pouvez également filtrer le carnet d’adresses pour inclure uniquement les utilisateurs compatibles SIP en définissant l’attribut 0x8000 (Include) dans la colonne **Flags** de l’attribut **msRTCSIP-PrimaryUserAddress** . Cela permet également d’exclure les comptes de service des fichiers du carnet d’adresses.

Après avoir modifié la table AbAttribute, vous pouvez actualiser les données de la table AbUserEntry en exécutant la commande **Update-CsUserDatabase** de l’applet de commande. Après la réplication du RÉPLICATEUR d’annuaires, vous pouvez mettre à jour le fichier dans le magasin de fichiers du serveur de carnet d’adresses en exécutant manuellement la commande cmdlet **UpdateCsAddressBook** .

<div>


> [!NOTE]  
> Le serveur frontal sur lequel le serveur du carnet d’adresses est placé ne peut pas être configuré par l’administratif. L’un d’eux est choisi lors du déploiement — généralement, le premier serveur frontal déployé. En cas d’échec, le service de carnet d’adresses va basculer vers un autre serveur frontal et ne requiert aucune intervention de l’administrateur.



</div>

<div>


> [!IMPORTANT]  
> Si vous avez consolidé ou modifié votre infrastructure par le biais d’un déploiement de forêts multiples ou d’un déploiement parent/enfant (par exemple, la consolidation de votre infrastructure avant de migrer vers Lync Server), il est possible que le téléchargement du service de carnet d’adresses et la requête Web du carnet d’adresses échouent pour certains utilisateurs. Dans un déploiement incluant plusieurs domaines ou forêts, l’attribut <STRONG>MsRTCSIP-OriginatorSid</STRONG> est rempli sur les objets utilisateur qui présentent le problème. Pour résoudre le problème, l’attribut <STRONG>MsRTCSIP-OriginatorSid</STRONG> doit être défini sur la valeur null.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

