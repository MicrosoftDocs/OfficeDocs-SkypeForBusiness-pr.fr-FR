---
title: Comment les photos d’utilisateur sont affichées dans Lync
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 941c1ab56feea557dfc792ea0af6415dd2a56851
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838872"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>Comment les photos d’utilisateur sont affichées dans Lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-08-25_

**Résumé:** Les photos des utilisateurs affichées dans le client Lync peuvent être différentes selon la fonctionnalité Lync que vous utilisez, par exemple, lors d’une conférence téléphonique ou d’une conversation par messagerie instantanée.

Lync 2010 a introduit la possibilité d’inclure une photo avec votre profil Lync qui s’affiche pour les autres utilisateurs Lync. Vous pouvez également choisir d’afficher ou non les photos de vos contacts dans le client Lync. Dans Lync 2013, prise en charge de photos haute résolution pour les utilisateurs. Cette rubrique décrit la façon dont le client Lync obtient et affiche les photos des utilisateurs, l’emplacement de stockage des images, les limitations pour chaque source d’image et la façon dont les photos des utilisateurs sont utilisées par différents services Lync.

<div>

## <a name="planning-considerations"></a>Considérations en matière de planification

Prenez en considération les points suivants lors de la planification de la prise en charge des photos des utilisateurs.

  - La prise en charge des photos haute définition nécessite que la boîte aux lettres de l’utilisateur soit située sur Exchange 2013 et le compte d’utilisateur Lync dans le pool 2013.

  - Les photos des utilisateurs haute définition sont uniquement prises en charge dans un environnement dans lequel Lync Server 2013 et Exchange 2013 sont utilisés.

  - Les utilisateurs dotés d’une boîte aux lettres sur Exchange 2010 utilisent toujours l’attribut **ThumbNailPhoto** d’AD DS comme source de la photo de l’utilisateur.

  - Une photo de l’utilisateur stockée en tant qu’attribut **ThumbNailPhoto** d’AD DS ne sera pas affichée pour les contacts externes/fédérés.

  - Si les photos des contacts de l’utilisateur sont stockées dans AD DS, le fichier image utilisé est limité à 96 x 96 pixels et ne dépasse pas la taille du fichier de 100 Ko.

  - Si la connectivité entre Lync Server et Exchange Server est perdue, le **ThumbNailPhoto** de la résolution basse de l’utilisateur à partir d’AD DS est affiché et ne peut être affiché qu’aux utilisateurs internes.

  - Les photos des utilisateurs haute résolution sont affichées dans les réunions 2013 Lync lorsque la vidéo n’est pas activée pour le haut-parleur actif. Par ailleurs, le déplacement de la souris sur la photo miniature dans la Galerie affiche la photo haute résolution.

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Photos des utilisateurs dans Lync 2010

Dans le client Lync 2010, vous avez le choix entre deux options pour afficher une photo de votre profil, une **image d’entreprise par défaut** et **afficher une image à partir d’une adresse Web**.

<div>

## <a name="default-corporate-picture"></a>Image d’entreprise par défaut

Lorsque vous choisissez l’option **d’image d’entreprise par défaut** , Lync obtient la photo qui vous est affichée dans les services de domaine Active Directory (AD FS). L’image utilisée est l’image définie en tant que valeur de l’attribut **ThumbNailPhoto** dans les services de domaine Active Directory (AD FS). Il s’agit du fichier utilisé par Exchange pour afficher des images dans Outlook.

Voici quelques éléments à prendre en compte lors de l’utilisation d’images provenant des services de domaine Active Directory:

  - Seules les images dont la taille ne doit pas être de 96 96 pixels sont prises en charge. La taille de fichier de l’image est limitée à 100 Ko.

  - Par défaut, les utilisateurs peuvent modifier l’image utilisée pour l’attribut **ThumbNailPhoto** , mais pas directement via le client Lync. Vous pouvez désactiver ce service via les services de domaine Active Directory.

  - Les images stockées dans les services de domaine Active Directory ne s’affichent pas pour les contacts externes à votre organisation, même s’ils sont des contacts fédérés.

  - Dans de grandes organisations, le stockage et la récupération des images pour de nombreux utilisateurs peuvent avoir un impact sur les performances et la taille de la base de données des services de domaine Active Directory.

  - La taille de fichier et les dimensions d’image limitées indiquent que seules les images de faible résolution peuvent être utilisées.

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>Comment les utilisateurs gèrent leurs photos utilisateur dans les services de domaine Active Directory (AD FS)

L’utilisateur ne peut pas modifier l’image utilisée dans son profil de services de domaine Active Directory directement via le client Lync 2010. Pour cela, vous pouvez utiliser l’une des options suivantes, le cas échéant:

  - ****   Les utilisateurs de SharePoint Server peuvent télécharger une photo sur’mon site’sur un serveur SharePoint, puis [configurer la synchronisation des profils dans SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) pour synchroniser la photo avec l’attribut **ThumbNailPhoto** dans le domaine Active Directory Services.

  - **Photo stockée sur des URL**   accessibles publiquement les utilisateurs peuvent configurer leur photo utilisateur en spécifiant une URL accessible publiquement pour l’image qu’ils souhaitent utiliser. L’image doit être accessible au public sans mot de passe. L’image stockée à l’adresse Web spécifiée est transférée à d’autres utilisateurs via la catégorie carte de contact des informations de présence. Lorsque le client Lync doit afficher une photo de l’utilisateur, il récupère l’image à partir de l’adresse Web spécifiée.

  - **Les applets de RecipientDataProperty 2010 Exchange pour les administrateurs Windows PowerShell**   peuvent exécuter l’applet de passe [Import-](http://go.microsoft.com/fwlink/p/?linkid=507468) dans Exchange 2010 Management Shell pour gérer l’attribut **ThumbNailPhoto** . Lorsque les images sont importées à l’aide des applets de applet de passe Exchange 2010, la taille du fichier est limitée à 10 Ko.

  - **Outils tiers les**   utilisateurs peuvent télécharger uniquement leur propre photo vers pour l’attribut **ThumbNailPhoto** .

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>Afficher une image à partir d’une adresse Web

Lorsque vous choisissez l’option **afficher une image à partir d’une adresse Web** , Lync obtient l’image à l’adresse que vous entrez et l’affiche pour votre photo de l’utilisateur dans Lync.

Voici quelques éléments à prendre en compte lors de l’utilisation d’images issues d’une adresse Web:

  - Les limites de taille de fichier sont déterminées par l’attribut **MaxPhotoSizeKB** dans la stratégie client, définie à l’aide de l’applet [de nouvelle cmdlet New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) . La taille limite par défaut est de 30 Ko. La valeur maximale est 100 Ko. Il n’existe aucune restriction sur la résolution de l’image, mais si vous essayez d’utiliser un fichier image dont la taille est supérieure à la limite de taille, elle ne sera pas téléchargée vers les clients Lync. Vous pouvez définir la valeur sur 0 pour désactiver l’utilisation de toutes les photos des utilisateurs dans Lync.

  - Les photos des utilisateurs d’une adresse Web peuvent être consultées par des contacts fédérés externes.

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>Gestion de la photo de l’utilisateur à l’aide des cmdlets de stratégie client

Dans Lync Server 2010, les paramètres de stratégie de client sont configurés avec les applets de fonction CsClientPolicy. Les paramètres de stratégie configurés sont envoyés aux clients par le biais de la mise en service intrabande. Les deux paramètres des cmdlets CsClientPolicy qui déterminent l’utilisation de la photo de l’utilisateur sont **DisplayPhoto** et **MaxPhotoSizeKB**. Le paramètre de mise en service intrabande correspondant pour **DisplayPhoto** et **MaxPhotoSizeKB** est appelé photousage. **** Les valeurs du **** paramètre photousage sont envoyées aux clients via le **EndpointConfiguration** **provisionGroup**. Pour plus d’informations, voir [vue d’ensemble des stratégies et des paramètres du client](http://go.microsoft.com/fwlink/?linkid=507470) .

La valeur du paramètre **DisplayPhoto** détermine la source de l’image photo de l’utilisateur. Les valeurs prises en charge sont indiquées dans le tableau suivant.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Valeur du paramètre DisplayPhoto</th>
<th>Source d’image</th>
<th>Paramètres du client Lync 2010</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NoPhoto</p></td>
<td><p>néant</p></td>
<td><p><strong>Ne pas afficher mon image</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>Image d’entreprise par défaut</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>Adresse Web</p></td>
<td><p><strong>Afficher une image à partir d’une adresse Web</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Comment le client 2010 Lync obtient des photos

Dans Lync 2010, les photos des utilisateurs sont gérées sur le serveur par le service de carnet d’adresses. Le client Lync obtient les photos des utilisateurs en interrogeant d’abord le service de requête sur le carnet d’adresses (ABWQ) sur le serveur, présenté par le biais du service Web d’extension de liste de distribution. Le client reçoit le fichier image, puis le copie dans le cache de l’utilisateur pour éviter de télécharger l’image chaque fois qu’il doit être affiché. Les valeurs d’attribut renvoyées par la requête sont également stockées dans l’entrée du service de carnet d’adresses mise en cache pour l’utilisateur. Le service de carnet d’adresses supprime toutes les images mises en cache toutes les 24 heures, ce qui signifie qu’il peut s’écouler jusqu’à 24 heures avant la mise à jour des nouvelles images utilisateur dans le cache du serveur. Vous pouvez forcer une mise à jour du cache à l’aide de l’applet de passe [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .

Les photos des utilisateurs incluses dans le statut de présence possèdent également une valeur de hachage associée que le client Lync utilise pour déterminer si une nouvelle image est disponible. Le client est automatiquement averti des modifications apportées au fichier image utilisé dans le statut de présence.

<div class=" ">


> [!NOTE]  
> Étant donné que les photos ne sont pas stockées dans la base de données GalContacts. DB, le téléchargement des photos des utilisateurs ne dépend pas du paramètre <STRONG>AddressBookAvailability</STRONG> dans la stratégie client (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).



</div>

La requête au service ABWQ inclut les attributs suivants:

  - ****   Photohachez la valeur de hachage des données de photo binaires et est utilisée pour déterminer si la photo actuelle a changé.

  - **PhotoRelPath**   chemin d’accès relatif du fichier image stocké sur le serveur.

  - ****   Photodimensionnez la taille du fichier image, en octets.

  - **** Date et heure auxquelles le fichier image a été téléchargé en dernier du serveur et copié dans le cache du client.   

Ensuite, après avoir récupéré le fichier image, le client 2010 Lync compare les valeurs d’attribut renvoyées par la requête par rapport aux valeurs d’attributs reçues par le client à partir de la mise en service intrabande pour voir s’il est différent. Si les valeurs sont différentes, le client récupère le fichier image de l’utilisateur connecté à l’aide d’une requête GET HTTP.

Par ailleurs, le client vérifie auprès du serveur toutes les 24 heures après l’heure de création de la version mise en cache du fichier image pour comparer la valeur de l' **** attribut photodièse sur le serveur avec la valeur sur le client. Si les valeurs sont différentes, le client sait que le fichier image a changé. Pour obtenir le fichier image mis à jour, le client interroge de nouveau le service ABWQ pour mettre à jour le fichier image dans le cache du client avec le fichier image sur le serveur, ce qui réinitialise également l' **horodatage** sur le fichier dans le cache client.

Voici un exemple de réponse à une requête sur le service ABWQ:

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

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a>Photos des utilisateurs dans Lync 2013

Lync 2013 a mis en place une prise en charge des images haute résolution pour les photos des utilisateurs. Lync 2013 inclut également la prise en charge du stockage de photos des utilisateurs dans la boîte aux lettres de l’utilisateur sur Exchange 2013, qui supprime les limitations de résolution et de taille d’image présentes dans Lync 2010. Les photos des utilisateurs dans Lync 2013 peuvent prendre jusqu’à 648 pixels par 648 pixels et disposer d’une taille de fichier pouvant atteindre 20 Mo. Les photos haute résolution de Lync 2013 doivent figurer dans la boîte aux lettres de l’utilisateur sur Exchange 2013 et ne sont prises en charge que par le client Lync 2013. Cette intégration avec Exchange tire parti de la nouvelle infrastructure d’autorisation incluse dans les versions 2013 de Lync, Exchange et SharePoint appelées OAuth.

Si Exchange 2013 n’est pas utilisé dans votre déploiement, la prise en charge des photos des utilisateurs est identique à celle de Lync 2010. Toutefois, les options utilisateur permettant de choisir la photo à utiliser diffèrent dans le client 2013 Lync. Dans le client Lync 2013, les utilisateurs peuvent sélectionner l’option **Masquer mon image** ou **afficher mon image**. L’option **afficher une image à partir d’un site Web** n’est pas disponible par défaut, mais peut être activée en assignant une stratégie client.

<div>

## <a name="hide-my-picture"></a>Masquer mon image

Les paramètres des photos des utilisateurs se trouvent dans la boîte de dialogue **options** de Lync 2013. Lorsque vous sélectionnez **Masquer mon image**, aucune photo de l’utilisateur ne s’affiche dans le client Lync, mais votre photo est toujours affichée sur votre carte de visite et en dehors de Lync.

</div>

<div>

## <a name="show-my-picture"></a>Afficher mon image

Lorsque vous sélectionnez l’option **afficher mon image** , la photo de l’utilisateur s’affiche dans votre client Lync et aux autres utilisateurs des conversations Lync. L’image utilisée est celle qui est stockée dans AD DS.

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>Afficher une image à partir d’un site Web

L’option **afficher l’image à partir d’un site Web** devient disponible dans Lync 2013 une fois qu’une stratégie client est définie pour l’activer. La version cliente doit être plus récente que 15.0.4535.1002, installée avec les [mises à jour cumulatives de Lync: 2013 de novembre](http://go.microsoft.com/fwlink/p/?linkid=509908). Les utilisateurs doivent se déconnecter, puis revenir de nouveau pour voir les modifications apportées au client.

Vous pouvez configurer la stratégie client pour qu’elle soit activée pour **afficher une image à partir d’un site Web** en exécutant la stratégie [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) dans Lync Server Management Shell. Les exemples d’applets de commande suivants montrent comment définir globalement la stratégie pour tous les utilisateurs de votre déploiement:

   ```
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```
    $po.PolicyEntry.Add($pe)
   ```

   ```
    Set-CsClientPolicy -Instance $po
   ```


Lorsqu’une image est téléchargée vers la boîte aux lettres de l’utilisateur, Exchange crée automatiquement une version de résolution plus basse de l’image qui peut être utilisée dans les applications clientes. La photo de l’utilisateur est également mise à jour dans AD DS.

<div class=" ">


> [!NOTE]  
> Lors de la mise à jour d’un fichier image dans AD DS, une image de pixel 48 x 48 est créée et utilisée pour le thumbnailPhoto dans AD DS. Toute image existante est remplacée. Par conséquent, si vous avez ajouté une image 96 x 96 dans AD DS, celle-ci sera remplacée par la nouvelle image 48 x 48. Ce n’est pas seulement important: vous avez des utilisateurs dans votre environnement utilisant les clients Lync 2010, car ils obtiendront les photos des utilisateurs d’AD DS. Vous pouvez importer des images de 96 x 96 pixels pour remplacer celles créées par AD DS si vous avez des clients Lync 2010 au sein de votre organisation.



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Support photo de l’utilisateur dans Lync 2013

Dans Lync 2013, trois résolutions d’image sont prises en charge pour les photos des utilisateurs, comme décrit dans le tableau suivant. L’image utilisée est déterminée par le paramètre de stratégie client attribué aux utilisateurs de Lync. Pour plus d’informations, voir la section «gestion de la photo de l’utilisateur avec les applets de stratégie client».


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Résolution d’image (pixels)</th>
<th>Application</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>Utilisé si aucune image de résolution plus élevée n’est sélectionnée</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>Utilisé dans Outlook Web App et Outlook 2013</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>Utilisé dans le client de bureau Lync 2013 et Lync 2013 Web App</p></td>
</tr>
</tbody>
</table>


Tout utilisateur disposant d’une boîte aux lettres activée dans Exchange 2013 peut télécharger une autre image, y compris des photos haute résolution, via les options client d’Outlook Web Access ou Lync 2013. Les paramètres recommandés pour les images utilisées sont les suivants:

  - **Résolution d’image**   648 par 648 pixels

  - **Palette de couleurs**   24 bits

  - **Taille de fichier d’image**   maximale de 20 Mo

  - **Format de fichier**   JPEG

Une image JPEG standard 24 bits d’une taille de 648 648 pixels, dont la taille est d’environ 240 Ko, est nécessaire pour les 4 Mo d’espace de stockage pour chaque photo de l’utilisateur.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

