---
title: Mode d’affichage des photos de l’utilisateur dans Lync
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
ms.openlocfilehash: 097262cc3a4ba4b56cd023bc5174d881426deff2
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137915"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>Mode d’affichage des photos de l’utilisateur dans Lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-08-25_

**Résumé :** Les photos des utilisateurs affichés dans le client Lync peuvent varier en fonction de la fonctionnalité Lync que vous utilisez, comme dans une conférence ou une conversation par messagerie instantanée.

Lync 2010 a introduit la possibilité d’inclure une photo avec votre profil Lync qui est affiché aux autres utilisateurs de Lync. Vous pouvez également choisir d’afficher ou non les photos de vos contacts dans le client Lync. Dans Lync 2013, la prise en charge de photos haute résolution pour les utilisateurs. Cette rubrique explique comment le client Lync obtient et affiche des photos de l’utilisateur, où les images sont stockées, les limites de chaque source d’image et comment les photos des utilisateurs sont utilisées par différents services Lync.

<div>

## <a name="planning-considerations"></a>Considérations sur la planification

Vous devez tenir compte des éléments suivants lors de la planification de l’implémentation de la prise en charge des photos des utilisateurs.

  - La prise en charge des photos haute définition nécessite que la boîte aux lettres de l’utilisateur se trouve sur Exchange 2013 et le compte d’utilisateur Lync dans le pool Lync 2013.

  - Les photos des utilisateurs de haute définition sont prises en charge uniquement dans un environnement où Lync Server 2013 et Exchange 2013 sont utilisés.

  - Les utilisateurs avec des boîtes aux lettres sur Exchange 2010 utiliseront toujours l’attribut **ThumbNailPhoto** de AD DS comme source de leur photo d’utilisateur.

  - Une photo d’utilisateur stockée en tant qu’attribut **ThumbNailPhoto** à partir d’AD DS ne sera pas affichée aux contacts externes/fédérés.

  - Si les photos des contacts de l’utilisateur sont stockées dans les services de domaine Active Directory, le fichier image utilisé est limité à 96 × 96 pixels et à une taille de fichier de 100 Ko.

  - Si la connectivité entre Lync Server et Exchange Server est perdue, la faible résolution **ThumbNailPhoto** de l’utilisateur à partir d’AD DS sera affichée, et uniquement pour les utilisateurs internes.

  - Les photos des utilisateurs à haute résolution sont affichées dans les réunions Lync 2013 lorsqu’un haut-parleur actif n’est pas activé pour la vidéo. En outre, si vous déplacez la souris sur une photo miniature de la Galerie, la photo haute résolution s’affiche.

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Photos de l’utilisateur dans Lync 2010

Dans le client Lync 2010, vous avez le choix entre deux options pour afficher la photo de votre profil, l' **image d’entreprise par défaut** et l’affichage **de l’image à partir d’une adresse Web**.

<div>

## <a name="default-corporate-picture"></a>Image d’entreprise par défaut

Lorsque vous choisissez l’option **d’image d’entreprise par défaut** , Lync obtient la photo affichée pour vous à partir des services de domaine Active Directory. L’image utilisée est l’image définie comme valeur de l’attribut **ThumbNailPhoto** dans les services de domaine Active Directory. Il s’agit du même fichier que celui utilisé par Exchange pour afficher des images dans Outlook.

Considérations relatives à l’utilisation d’images à partir des services de domaine Active Directory :

  - Seules les images avec des dimensions jusqu’à 96 pixels par 96 pixels sont prises en charge. La taille de fichier de l’image est limitée à 100 Ko.

  - Par défaut, les utilisateurs peuvent modifier l’image utilisée pour l’attribut **ThumbNailPhoto** , mais pas directement via le client Lync. Vous pouvez le désactiver par le biais des services de domaine Active Directory.

  - Les images stockées dans les services de domaine Active Directory ne sont pas affichées aux contacts externes à votre organisation, même s’il s’agit de contacts fédérés.

  - Dans les grandes organisations, le stockage et l’extraction des images pour un grand nombre d’utilisateurs peuvent avoir un impact sur la taille et les performances de la base de données des services de domaine Active Directory.

  - Les dimensions limitées de l’image et de la taille des fichiers signifient que seules les images à faible résolution peuvent être utilisées.

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>Comment les utilisateurs gèrent leurs photos utilisateur dans les services de domaine Active Directory

L’utilisateur ne peut pas modifier l’image utilisée dans son profil des services de domaine Active Directory directement via le client Lync 2010. Ils peuvent utiliser l’une des options suivantes pour le faire, le cas échéant :

  - **Les utilisateurs SharePoint Server**   peuvent télécharger une photo sur un « mon site » sur un serveur SharePoint, puis [configurer la synchronisation des profils dans SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) pour synchroniser la photo avec l’attribut **ThumbNailPhoto** dans les services de domaine Active Directory.

  - **Photo stockée sur une URL**   accessible publiquement les utilisateurs peuvent configurer leur photo utilisateur en spécifiant une URL accessible publiquement pour l’image qu’ils souhaitent utiliser. L’image doit être accessible publiquement sans mot de passe. L’image stockée à l’adresse Web spécifiée est transférée aux autres utilisateurs par le biais de la catégorie de carte de visite dans les informations de présence. Lorsque le client Lync a besoin d’afficher une photo de l’utilisateur, il récupère l’image à partir de l’adresse Web spécifiée.

  - **Les applets de commande Exchange 2010 pour les administrateurs Windows PowerShell**   peuvent exécuter l’applet de commande [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) dans Exchange 2010 Management Shell dans pour gérer l’attribut **ThumbNailPhoto** . Lorsque des images sont importées avec des applets de commande Exchange 2010, la taille du fichier est limitée à 10 Ko.

  - **Outils tiers les**   utilisateurs peuvent télécharger uniquement leur propre photo vers pour l’attribut **ThumbNailPhoto** .

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>Afficher une image à partir d’une adresse web

Lorsque vous choisissez l’option **afficher une image à partir d’une adresse Web** , Lync obtient l’image à l’adresse que vous entrez et l’affiche pour votre photo de l’utilisateur dans Lync.

Les éléments à prendre en compte pour l’utilisation d’images à partir d’une adresse Web sont les suivants :

  - Les limites de taille de fichier sont déterminées par l’attribut **MaxPhotoSizeKB** dans la stratégie client, définie à l’aide de la cmdlet [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) . La limite de taille par défaut est de 30 Ko. La valeur maximale est 100 Ko. Il n’existe aucune restriction quant à la résolution de l’image, mais si vous essayez d’utiliser un fichier image qui dépasse la limite de taille, il ne sera pas téléchargé sur les clients Lync. Vous pouvez définir la valeur sur 0 pour désactiver l’utilisation de toutes les photos des utilisateurs dans Lync.

  - Les photos des utilisateurs d’une adresse Web peuvent être vues par des contacts fédérés externes.

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>Gestion de la photo de l’utilisateur avec des applets de commande de stratégie client

Dans Lync Server 2010, les paramètres de stratégie client sont configurés avec les applets de commande CsClientPolicy. Les paramètres de stratégie configurés sont envoyés aux clients via la mise en service intrabande. Les deux paramètres des cmdlets CsClientPolicy qui déterminent l’expérience de photo de l’utilisateur sont **DisplayPhoto** et **MaxPhotoSizeKB**. Le paramètre de mise en service intrabande correspondant pour **DisplayPhoto** et **MaxPhotoSizeKB** est appelé **photousage**. Les valeurs du paramètre de **photoutilisation** sont envoyer aux clients via le **EndpointConfiguration** **provisionGroup**. Pour plus d’informations, voir [Overview of client Policies and Settings](https://go.microsoft.com/fwlink/?linkid=507470) .

La valeur du paramètre **DisplayPhoto** détermine la source de l’image photo de l’utilisateur. Les valeurs prises en charge sont incluses dans le tableau suivant.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Valeur du paramètre DisplayPhoto</th>
<th>Source de l’image</th>
<th>Paramètres du client Lync 2010</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NoPhoto</p></td>
<td><p>none</p></td>
<td><p><strong>Ne pas afficher mon image</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>Image d’entreprise par défaut</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>Adresse Web</p></td>
<td><p><strong>Afficher une image à partir d’une adresse web</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Comment Lync 2010 client obtient des photos

Dans Lync 2010, les photos des utilisateurs sont gérées sur le serveur par le service de carnet d’adresses. Le client Lync obtient des photos de l’utilisateur en interrogeant d’abord le service de requête Web de carnet d’adresses (ABWQ) sur le serveur, qui est exposé via le service Web de développement de liste de distribution. Le client reçoit le fichier image, puis le copie dans le cache de l’utilisateur pour éviter de télécharger l’image à chaque fois qu’il doit être affiché. Les valeurs d’attribut renvoyées par la requête sont également stockées dans l’entrée du service de carnet d’adresses mis en cache pour l’utilisateur. Le service de carnet d’adresses supprime toutes les images mises en cache toutes les 24 heures, ce qui signifie qu’il peut mettre jusqu’à 24 heures pour que les nouvelles images utilisateur soient mises à jour dans le cache du serveur. Vous pouvez forcer une mise à jour du cache à l’aide de la cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .

Les photos des utilisateurs incluses dans le statut de présence ont également une valeur de hachage associée que le client Lync utilise pour déterminer s’il existe une image plus récente disponible. Le client est automatiquement informé des modifications apportées au fichier image utilisé dans l’état de présence.

<div class=" ">


> [!NOTE]  
> Étant donné que les photos ne sont pas stockées dans la base de données GalContacts. DB, le téléchargement des photos des utilisateurs n’est pas dépendant du paramètre <STRONG>AddressBookAvailability</STRONG> dans la stratégie client (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).



</div>

La requête au service ABWQ inclut les attributs suivants :

  - **Photodièse**   la valeur de hachage des données de la photo binaire et est utilisée pour déterminer si la photo active a été modifiée.

  - **PhotoRelPath**   chemin d’accès relatif au fichier image stocké sur le serveur.

  - **Photosize**   taille du fichier image, en octets.

  - **TimeStamp**   date et heure du dernier téléchargement du fichier image à partir du serveur et copié dans le cache client.

Ensuite, après avoir extrait le fichier image, le client Lync 2010 compare les valeurs d’attribut retournées par la requête aux valeurs d’attribut reçues par le client à partir de la mise en service intrabande afin de déterminer si elles sont différentes. Si les valeurs sont différentes, le client récupère le fichier image de l’utilisateur connecté à l’aide d’une demande HTTP GET.

En outre, le client vérifie avec le serveur toutes les 24 heures après l’heure à laquelle la version mise en cache du fichier image a été créée pour comparer la valeur de l’attribut de **photohachage** sur le serveur avec la valeur sur le client. Si les valeurs sont différentes, le client sait que le fichier image a été modifié. Pour obtenir le fichier image mis à jour, le client interroge à nouveau le service ABWQ afin de mettre à jour le fichier image dans le cache client avec le fichier image sur le serveur, ce qui réinitialise également l' **horodatage** du fichier dans le cache client.

Voici un exemple de réponse à une requête vers le service ABWQ :
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

## <a name="user-photos-in-lync-2013"></a>Photos de l’utilisateur dans Lync 2013

Lync 2013 a introduit une prise en charge pour les images haute résolution pour les photos des utilisateurs. Lync 2013 prend également en charge le stockage des photos des utilisateurs dans la boîte aux lettres de l’utilisateur sur Exchange 2013, ce qui supprime la résolution d’image et les limitations de taille présentes dans Lync 2010. Les photos des utilisateurs dans Lync 2013 peuvent atteindre 648 pixels par 648 pixels avec une taille de fichier maximale de 20 Mo. Les photos haute résolution dans Lync 2013 doivent se trouver dans la boîte aux lettres de l’utilisateur sur Exchange 2013 et sont prises en charge uniquement avec le client Lync 2013. Cette intégration avec Exchange tire parti de la nouvelle infrastructure d’autorisation incluse dans les versions 2013 de Lync, Exchange et SharePoint, appelée OAuth.

Si Exchange 2013 n’est pas utilisé dans votre déploiement, la prise en charge des photos des utilisateurs est identique à celle de Lync 2010. Toutefois, les options utilisateur permettant de choisir la photo à utiliser sont différentes dans Lync 2013 client. Dans le client Lync 2013, les utilisateurs peuvent sélectionner **Masquer mon image** ou **afficher mon image**. L’option **afficher une image d’un site Web** n’est pas disponible par défaut, mais peut être activée en affectant une stratégie client.

<div>

## <a name="hide-my-picture"></a>Masquer mon image

Les paramètres pour les photos des utilisateurs figurent dans la boîte de dialogue **options** de Lync 2013. Lorsque vous sélectionnez **Masquer mon image**, aucune photo de l’utilisateur n’est affichée dans le client Lync, mais votre photo est toujours affichée sur la carte de visite et en dehors de Lync.

</div>

<div>

## <a name="show-my-picture"></a>Afficher mon image

Lorsque vous choisissez l’option **afficher mon image** , votre photo de l’utilisateur s’affiche dans votre client Lync et aux autres utilisateurs dans les conversations Lync. L’image utilisée est celle stockée dans les services de domaine Active Directory (AD DS).

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>Afficher une image à partir d’un site Web

L’option **afficher l’image d’un site Web** devient disponible dans Lync 2013 une fois qu’une stratégie client est configurée pour l’activer. La version du client doit être plus récente que 15.0.4535.1002, qui est installée avec les [mises à jour cumulatives Lync : novembre 2013](https://go.microsoft.com/fwlink/p/?linkid=509908). Il se peut que les utilisateurs doivent se déconnecter puis se reconnecter pour voir les modifications apportées au client.

Vous pouvez définir la stratégie client pour activer l' **affichage des images à partir d’un paramètre de site Web** en exécutant la stratégie [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) dans Lync Server Management Shell. Les exemples de cmdlets suivants montrent comment définir la stratégie globalement pour tous les utilisateurs de votre déploiement :

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


Lorsqu’une image est chargée dans la boîte aux lettres de l’utilisateur, Exchange crée automatiquement une version moins élevée de l’image qui peut être utilisée dans les applications clientes. La photo de l’utilisateur est également mise à jour dans AD DS.

<div class=" ">


> [!NOTE]  
> Lorsqu’un fichier image est mis à jour dans AD DS, une image 48 x 48 pixel est créée et utilisée pour le thumbnailPhoto dans AD DS. Toutes les images existantes sont remplacées. Par conséquent, si vous avez ajouté une image 96 x 96 à AD DS, celle-ci sera remplacée par la nouvelle image 48 x 48. Cette opération n’est importante que si vous avez des utilisateurs dans votre environnement utilisant des clients Lync 2010, car ces clients obtiendront des photos de l’utilisateur dans AD DS. Vous pouvez importer des images 96 x 96 pixels pour remplacer celles créées par AD DS si vous avez des clients Lync 2010 dans votre organisation.



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Prise en charge des photos de l’utilisateur dans Lync 2013

Dans Lync 2013, trois résolutions d’image sont prises en charge pour les photos des utilisateurs, comme décrit dans le tableau suivant. L’image utilisée est déterminée par le paramètre de stratégie client attribué aux utilisateurs Lync. Pour plus d’informations, consultez la rubrique sur la gestion de la photo de l’utilisateur avec des applets de commande de stratégie client.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Résolution de l’image (pixels)</th>
<th>Application</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>Utilisé si aucune image de résolution supérieure n’est sélectionnée</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>Utilisé dans Outlook Web App et Outlook 2013</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>Utilisé dans le client de bureau Lync 2013 et dans Lync 2013 Web App</p></td>
</tr>
</tbody>
</table>


Tout utilisateur disposant d’une boîte aux lettres activée dans Exchange 2013 peut télécharger une autre image, y compris des photos haute résolution, via les options du client Outlook Web Access ou Lync 2013. Les paramètres recommandés pour les images utilisées sont les suivants :

  - **Résolution**   de l’image 648 par 648 pixels

  - **Profondeur de couleur**   24 bits

  - **Taille de fichier image**   pouvant atteindre 20 Mo

  - **Format**   JPEG de format de fichier

Une image JPEG standard de 24 bits 648 pixels par 648 pixels a une taille d’environ 240 Ko, de sorte que 1 Mo d’espace de stockage est nécessaire pour 4 photos utilisateur.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

