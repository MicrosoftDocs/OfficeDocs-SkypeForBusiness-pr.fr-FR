---
title: Administration du service de carnet d’adresses dans Lync Server 2013
TOCTitle: Administration du service de carnet d’adresses dans Lync Server 2013
ms:assetid: 801e4243-9670-4477-aa2f-88b61ecf5351
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg429711(v=OCS.15)
ms:contentKeyID: 49297886
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Administration du service de carnet d’adresses dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Dans le cadre du déploiement de Lync Server, Enterprise Edition ou serveur Standard Edition, le service de carnet d’adresses est installé par défaut. La base de données utilisée par le service de carnet d’adresses (RTCab) est créée sur le serveur SQL Server (pour le Enterprise Edition, il s’agit du serveur SQL Server principal, pour le serveur Standard Edition, du serveur SQL Server colocalisé).

> [!NOTE]  
> Pour plus d'informations sur l'utilisation de l'<strong>Éditeur ADSI</strong> pour éditer des attributs d'objets services de domaine Active Directory, voir <a href="http://go.microsoft.com/fwlink/?linkid=330427">Éditeur ADSI</a>. Pour plus d'informations sur un outil dans le kit des ressources, notamment pour le service du carnet d'adesses, voir <a href="http://go.microsoft.com/fwlink/?linkid=330429">Microsoft Lync Server 2013 Resource Kit Tools</a>.

## Normalisation des numéros de téléphone du serveur de carnet d’adresses

Lync Server nécessite des numéros de téléphone au standard RFC 3966/E.164. Pour utiliser des numéros de téléphone non structurés ou formatés de manière incohérente, Lync Server s’appuie sur le serveur de carnet d’adresses pour prétraiter les numéros de téléphone avant qu’ils ne soient transmis aux règles de normalisation. Lorsqu’un numéro de téléphone est utilisé à partir du carnet d’adresses et que la règle de normalisation est appliquée, les clients (par exemple, Lync Phone Edition et Lync Mobile) peuvent utiliser ces numéros normalisés.

Les règles de normalisation utilisées dans les versions précédentes risquent de ne pas fonctionner correctement sans quelques ajustements. Du fait que les espaces et les caractères non obligatoires sont supprimés avant d’appliquer les règles de normalisation, si votre expression regex recherche spécifiquement un tiret ou tout autre caractère ayant été supprimé, votre règle de normalisation risque d’échouer. Vous devriez passer en revue vos règles de normalisation pour vous assurer qu’elles ne recherchent pas ces caractères non obligatoires, ou que la règle peut échouer normalement et se poursuivre au cas où le caractère soit absent et que la règle anticipe sa présence.

## Réplicateur d’utilisateurs et serveur de carnet d’adresses

Le serveur de carnet d’adresses utilise les données fournies par le réplicateur d’utilisateurs pour mettre à jour les informations obtenues initialement de la liste d’adresses globale. Le réplicateur d’utilisateurs écrit les attributs des services de domaine Active Directory pour chaque utilisateur, contact et groupe dans la table AbUserEntry de la base de données, le serveur de carnet d’adresses synchronise les données utilisateur à partir de la base de données dans les fichiers du magasin de fichiers du serveur de carnet d’adresses, puis dans la base de données de carnet d’adresses RTCab. Le schéma pour la table AbUserEntry utilise deux colonnes : **Guid utilisateur** et **Données utilisateur**. **Guid utilisateur** représente la colonne d’index et contient le GUID sur 16 octets de l’objet Active Directory. **Données utilisateur** est une colonne image qui contient tous les attributs des services de domaine Active Directory mentionnés précédemment pour ce contact.

Le réplicateur d’utilisateurs détermine quels attributs Active Directory écrire en lisant une table de configuration située dans la même instance SQL Server que la table AbUserEntry. La table AbAttribute contient trois colonnes : **ID**, **Nom**, **Indicateurs**et **Activer**. La table est créée pendant la configuration de la base de données. Si la table AbAttribute est vide, le réplicateur d’utilisateurs ignore la logique de traitement de sa table AbUserEntry. Les attributs du serveur de carnet d’adresses sont dynamiques et récupérés à partir de la table AbAttribute, créée initialement par le serveur de carnet d’adresses à l’activation de ce dernier.

L’activation du serveur de carnet d’adresses renseigne la table AbAttribute avec les valeurs figurant dans le tableau suivant.


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
<td><p>2</p></td>
<td><p>Sn</p></td>
<td><p>0x02400000</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>displayName</p></td>
<td><p>0x03420000</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>Title</p></td>
<td><p>0x04000000</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>mailNickname</p></td>
<td><p>0x05400000</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>Company</p></td>
<td><p>0x06000000</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>physicalDeliveryOfficeName</p></td>
<td><p>0x07000000</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>msRTCSIP-PrimaryUserAddress</p></td>
<td><p>0x08520C00</p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>telephoneNumber</p></td>
<td><p>0x09022800</p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>homePhone</p></td>
<td><p>0x0A302800</p></td>
</tr>
<tr class="odd">
<td><p>11</p></td>
<td><p>Mobile</p></td>
<td><p>0x0B622800</p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
<td><p>otherTelephone</p></td>
<td><p>0x0C302000</p></td>
</tr>
<tr class="odd">
<td><p>13</p></td>
<td><p>ipPhone</p></td>
<td><p>0x0D302000</p></td>
</tr>
<tr class="even">
<td><p>14</p></td>
<td><p>Mail</p></td>
<td><p>0x0E500000</p></td>
</tr>
<tr class="odd">
<td><p>15</p></td>
<td><p>groupType</p></td>
<td><p>0x0F010800</p></td>
</tr>
<tr class="even">
<td><p>16</p></td>
<td><p>Department</p></td>
<td><p>0x10000000</p></td>
</tr>
<tr class="odd">
<td><p>17</p></td>
<td><p>Description</p></td>
<td><p>0x11000100</p></td>
</tr>
<tr class="even">
<td><p>18</p></td>
<td><p>Manager</p></td>
<td><p>0x12040001</p></td>
</tr>
<tr class="odd">
<td><p>19</p></td>
<td><p>proxyAddress</p></td>
<td><p>0x00500105</p></td>
</tr>
<tr class="even">
<td><p>20</p></td>
<td><p>msExchHideFromAddressLists</p></td>
<td><p>0xFF000003</p></td>
</tr>
<tr class="odd">
<td><p>99</p></td>
<td><p>entryID</p></td>
<td><p>0x99000000</p></td>
</tr>
</tbody>
</table>


Les numéros dans la colonne **ID** doivent être uniques et ne jamais être réutilisés. Le fait de garder des valeurs d’ID inférieures à 256 permet également d’économiser de l’espace dans les fichiers de sortie créés par le serveur de carnet d’adresses. Toutefois, la valeur d’ID maximale est de 65 535. La colonne **Nom** correspond au nom de l’attribut Active Directory que le réplicateur d’utilisateurs doit ajouter dans la table AbUserEntry pour chaque contact. La valeur dans la colonne **Indicateurs** sert à définir le type d’attribut. Les types d’attributs de serveur de carnet d’adresses suivants sont reconnus par le réplicateur d’utilisateurs, indiqué par l’octet bas de la valeur dans la colonne **Indicateurs**.


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
<td><p>Attribut de chaîne. Le réplicateur d’utilisateurs convertit ce type au format UTF-8 avant de le stocker dans la table AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x1</p></td>
<td><p>Attribut binaire. Le réplicateur d’utilisateurs stocke cet attribut dans le blob sans aucune conversion.</p></td>
</tr>
<tr class="odd">
<td><p>0x2</p></td>
<td><p>Attribut de chaîne inclus uniquement si la valeur d’attribut commence par « tel: ». Cela concerne principalement les attributs de chaîne à plusieurs valeurs, notamment les <strong>adresses proxy</strong>. Dans ce cas, le serveur de carnet d’adresses s’intéresse seulement aux entrées d’<strong>adresses proxy</strong> qui commencent par « tel: ». Par conséquent, afin de gagner de la place, le réplicateur d’utilisateurs stocke uniquement les entrées qui commencent par « tel: ».</p></td>
</tr>
<tr class="even">
<td><p>0x3</p></td>
<td><p>Attribut de chaîne booléen qui, s’il présente la valeur TRUE, empêche au réplicateur d’utilisateurs d’inclure ce contact dans la table AbUserEntry. Si sa valeur est FALSE, cela empêche le réplicateur d’utilisateurs d’inclure les attributs de ce contact dans la table AbUserEntry, mais pas l’attribut spécifique comportant cet indicateur. Il s’agit d’un autre cas spécifique qui concerne principalement l’attribut <strong>msExchHideFromAddressLists</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>0x4</p></td>
<td><p>Attribut de chaîne inclus uniquement si la valeur d’attribut commence par « smtp: » et inclut le symbole « @ ».</p></td>
</tr>
<tr class="even">
<td><p>0x5</p></td>
<td><p>Attribut de chaîne inclus uniquement si la valeur d’attribut commence par « tel: » ou « smtp: » et inclut le symbole « @ ».</p></td>
</tr>
<tr class="odd">
<td><p>0x100</p></td>
<td><p>S’il est défini, cet attribut à plusieurs valeurs peut apparaître plusieurs fois pour chaque contact.</p></td>
</tr>
<tr class="even">
<td><p>0x400</p></td>
<td><p>S’il est défini, permet d’identifier l’attribut du nom du compte d’utilisateur de messagerie pour un contact. Le serveur de carnet d’adresses utilise cet indicateur pour identifier la valeur d’attribut à afficher dans l’entrée du journal des événements de normalisation téléphonique.</p></td>
</tr>
<tr class="odd">
<td><p>0x800</p></td>
<td><p>S’il est défini, permet d’identifier un attribut requis pour un contact. Le serveur de carnet d’adresses ajoute un utilisateur dans la table AbUserEntry seulement si une valeur existe pour cet attribut dans Active Directory. S’il existe plusieurs attributs requis, seul l’un d’entre eux est nécessaire pour disposer d’une valeur afin d’inclure l’utilisateur dans la table AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x1000</p></td>
<td><p>S’il est défini, le serveur de carnet d’adresses normalise toujours la valeur de cet attribut.</p></td>
</tr>
<tr class="odd">
<td><p>0x2000</p></td>
<td><p>S’il est défini, le serveur de carnet d’adresses utilise le numéro normalisé des <strong>adresses proxy</strong>, si le paramètre CMS <strong>UseNormalizationRules</strong> présente la valeur FALSE, sinon il se comporte comme si le bit d’indicateur était 0x1000.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>S’il est défini, le serveur de carnet d’adresses n’inclut pas d’objets dans la table AbUserEntry qui contiennent cette valeur pour l’attribut spécifié. Par exemple, si l’attribut <strong>msRTCSIP-PrimaryUserAddress</strong> a ce bit d’indicateur défini, les contacts disposant de cet attribut ne sont alors pas créés dans la base de données.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>S’il est défini, le serveur de carnet d’adresses n’inclut pas d’objets dans la table AbUserEntry qui ne contiennent pas cette valeur pour l’attribut spécifié. Si les deux bits d’indicateur 0x4000 et 0x8000 sont définis sur un objet, l’attribut avec la valeur de bit d’indicateur définie sur 0x4000 est prioritaire et l’objet est exclu de la table AbUserEntry.</p></td>
</tr>
<tr class="even">
<td><p>0x10000</p></td>
<td><p>Représente un objet de groupe s’il est défini. Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour inclure les contacts avec l’attribut <strong>groupType</strong> dont la présence indique un groupe (par exemple, une liste de distribution ou un groupe de sécurité).</p></td>
</tr>
<tr class="odd">
<td><p>0x20000</p></td>
<td><p>S’il est défini, le réplicateur d’utilisateurs utilise ce bit d’indicateur pour inclure cet attribut dans les fichiers du serveur de carnet d’adresses propres au périphérique (c’est-à-dire les fichiers avec l’extension .dabs).</p></td>
</tr>
</tbody>
</table>


Dans les versions précédentes de Lync Server, lors de la modification d’Active Directory, l’administrateur devait exécuter les applets de commande **Update -CSUserDatabase** et **Update –CSAddressBook**Windows PowerShell pour rendre la modification persistante dans la base de données utilisateur Lync Server et la base de données RTCab. Dans Lync Server 2013, le réplicateur d’utilisateurs Lync Server récupèrera les modifications d’Active Directory et mettra à jour la base de données utilisateur Lync Server selon un intervalle configuré. Le réplicateur d’utilisateurs Lync Server propagera rapidement ces modifications dans la base de données RTCab sans que l’administrateur exécute Update-CSAddressBook. Si l’interrogation Web du carnet d’adresses est activée, les modifications seront appliquées aux résultats de recherche par les clients Lync. Les administrateurs devront exécuter Update -CSAddressBook si le téléchargement du fichier de carnet d’adresses est activé.

> [!NOTE]  
> Par défaut, le réplicateur d’utilisateurs Lync Server s’exécute toutes les 5 minutes. Vous pouvez configurer cet intervalle avec Set -CSUserReplicatorConfiguration -ReplicationCycleInterval &lt;&gt;.

## Filtrage du carnet d’adresses

Les utilisateurs renseignés dans les fichiers du serveur de carnet d’adresses peuvent être contrôlés en fonction de certains attributs services de domaine Active Directory répertoriés dans la table AbAttribute. Parmi les attributs utilisés pour le filtrage figure l’attribut **msExchangeHideFromAddressBook**. Il s’agit d’un attribut utilisateur ajouté par le schéma Exchange. Si la valeur de cet attribut est TRUE, le serveur Exchange Server utilise cet attribut pour masquer le contact dans la liste d’adresses globale d’Outlook. De même, si la valeur de cet attribut est TRUE, le réplicateur d’utilisateurs n’inclut pas cet utilisateur dans la table AbUserEntry qui sera également absent des fichiers du serveur de carnet d’adresses.

Vous pouvez utiliser certains bits d’indicateur pour définir un filtre à utiliser sur les attributs du serveur de carnet d’adresses. Par exemple, la présence de certains bits d’indicateurs peut identifier un attribut comme étant un attribut à inclure ou à exclure. Le réplicateur d’utilisateurs filtre les contacts contenant un attribut à exclure et ceux ne contenant pas d’attribut à inclure.

> [!WARNING]  
> Pour plus d'informations sur le filtrage du carnet d'adresses, voir <a href="https://technet.microsoft.com/en-us/library/gg415643(v=ocs.15)">Cmdlets pour le serveur de carnet d’adresses</a> et <a href="http://go.microsoft.com/fwlink/?linkid=330430">Filter Lync 2013 address book</a>

Il existe actuellement trois filtres différents. Le tableau suivant les répertorie.


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
<td><p>S’il est défini, permet d’identifier un attribut requis pour un contact. Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour filtrer les contacts qui ne contiennent pas au moins un attribut obligatoire. OuPathId est un attribut obligatoire, toujours défini. Au moins un des autres attributs obligatoires doit donc être défini. Sinon, le contact (c’est-à-dire avec la valeur de l’attribut obligatoire OuPathId) ne sera toujours pas ajouté à la base de données. Par exemple, si <strong>telephoneNumber</strong> et <strong>homePhone</strong> sont définis comme attributs obligatoires, seuls les contacts contenant au moins un de ces attributs sont ajoutés à la base de données.</p></td>
</tr>
<tr class="even">
<td><p>0x4000</p></td>
<td><p>Identifie un attribut à exclure s’il est défini. Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour filtrer les contacts qui contiennent cet attribut. Par exemple, si <strong>msRTCSIP-PrimaryUserAddress</strong> est défini en tant qu’attribut à exclure, les contacts disposant de cet attribut ne sont pas créés dans la base de données.</p></td>
</tr>
<tr class="odd">
<td><p>0x8000</p></td>
<td><p>Identifie un attribut à inclure s’il est défini. Le réplicateur d’utilisateurs utilise ce bit d’indicateur pour filtrer les contacts qui ne contiennent pas cet attribut. Par exemple, si <strong>msRTCSIP-PrimaryUserAddress</strong> est défini en tant qu’attribut à inclure, les contacts disposant de cet attribut sont ajoutés à la base de données.</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Si les deux bits d’indicateur 0x4000 (attribut à exclure) et 0x8000 (attribut à inclure) sont définis, le bit 0x4000 remplace le bit 0x8000 et le contact est exclu.

Même si vous pouvez filtrer le carnet d’adresses afin de n’inclure que certains utilisateurs, la limitation des entrées n’empêche pas les autres utilisateurs de contacter les utilisateurs filtrés ou d’afficher leur statut de présence. Les utilisateurs peuvent toujours rechercher, envoyer des messages instantanés ou initier manuellement des appels pour les utilisateurs absents du carnet d’adresses en entrant le nom de connexion complet d’un utilisateur. Les informations de contact d’un utilisateur peuvent également être trouvées dans Outlook.

Bien que le fait de disposer d’enregistrements de contacts complets dans les fichiers du carnet d’adresses vous permettent d’utiliser Lync Server pour initier des appels par courrier électronique, téléphone ou Voix Entreprise (si Voix Entreprise est activé sur le serveur, évidemment) avec des utilisateurs non configurés pour le protocole SIP, certaines organisations préfèrent inclure uniquement les utilisateurs activés pour SIP dans les entrées de leur serveur de carnet d’adresses. Vous pouvez filtrer le carnet d’adresses de manière à inclure uniquement les utilisateurs activés pour SIP en effaçant le bit 0x800 dans la colonne **Indicateurs** des attributs obligatoires suivants : **mailNickname**, **telephoneNumber**, **homePhone** et **mobile**. Vous pouvez également filtrer le carnet d’adresses de manière à inclure uniquement les utilisateurs activés pour SIP en définissant le bit 0x8000 (attribut à inclure) dans la colonne **Indicateurs** de l’attribut **msRTCSIP-PrimaryUserAddress**. Cela permet également d’exclure les comptes de service des fichiers du carnet d’adresses.

Après avoir modifié la table AbAttribute, vous pouvez actualiser les données de la table AbUserEntry en exécutant la commande de l’applet de commande **Update-CsUserDatabase**. Une fois que la réplication du réplicateur d’utilisateurs est terminée, vous pouvez mettre à jour le fichier dans le magasin de fichiers du serveur de carnet d’adresses en exécutant manuellement la commande de l’applet de commande **UpdateCsAddressBook**.

> [!NOTE]  
> Le serveur frontal sur lequel est placé le serveur de carnet d’adresses n’est pas configurable administrativement. Un serveur est choisi au cours du déploiement, il s’agit généralement du premier serveur frontal déployé. En cas d’échec, le service de carnet d’adresses passe sur un autre serveur frontal, sans qu’aucune attention administrative ne soit nécessaire.

> [!IMPORTANT]  
> Si vous avez consolidé ou modifié votre infrastructure à partir d’un déploiement multi-forêts ou d’un déploiement parent/enfant (par exemple en consolidant votre infrastructure avant de passer à Lync Server), le téléchargement du service de carnet d’adresses et le service de requête web du carnet d’adresses risquent d’échouer pour certains utilisateurs. Lorsqu’il se trouve dans un déploiement comportant plusieurs domaines ou forêts, l’attribut <strong>MsRTCSIP-OriginatorSid</strong> est renseigné sur les objets utilisateur qui rencontrent ce problème. L’attribut <strong>MsRTCSIP-OriginatorSid</strong> doit être défini avec la valeur NULL sur ces objets pour résoudre le problème.
