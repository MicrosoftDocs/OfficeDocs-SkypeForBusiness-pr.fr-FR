---
title: Comment les photos d’utilisateur sont affichées dans Lync
TOCTitle: Comment les photos d’utilisateur sont affichées dans Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62831961
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Comment les photos d’utilisateur sont affichées dans Lync

 

_**Dernière rubrique modifiée :** 2016-12-08_

**Récapitulatif :** Les photos des utilisateurs affichées dans le client Lync peuvent différer selon les fonctions Lync utilisées, par exemple, en conférence ou en conversion par messagerie instantanée.

Lync 2010 a introduit la possibilité d’inclure une photo dans votre profil Lync, visible par les autres utilisateurs Lync. Vous pouvez également choisir d’afficher ou non les photos à l’attention de vos contacts dans le client Lync. Dans Lync 2013, les photos d’utilisateur haute résolution sont prises en charge. Cette rubrique décrit comment le client Lync obtient les photos d’utilisateur et les affiche, indique l’emplacement de stockage des images, les limites de chaque source d’images et l’utilisation des photos d’utilisateur par les différents services Lync.

## Considérations relatives à la planification

Lorsque vous envisagez de mettre en œuvre la prise en charge des photos d’utilisateurs, vous devez prendre en compte les aspects suivants.

  - La prise en charge des photos d’utilisateur haute définition implique que la boîte aux lettres de l’utilisateur se trouve dans Exchange 2013 et que le compte d’utilisateur Lync se trouve dans le pool Lync 2013.

  - Les photos d’utilisateur haute définition ne sont prises en charge que dans un environnement utilisant Lync Server 2013 et Exchange 2013.

  - Les utilisateurs possédant des boîtes aux lettres Exchange 2010 continueront à utiliser l’attribut **thumbnailPhoto** des services de domaine Active Directory comme source de leurs photos d’utilisateur.

  - Une photo d’utilisateur stockée en tant qu’attribut **thumbnailPhoto** à partir des services de domaine Active Directory ne sera pas visible par les contacts externes/fédérés.

  - Si les photos des contacts d’un utilisateur sont stockées dans les services de domaine Active Directory, le fichier image utilisé est limité à 96 × 96 pixels et à une taille maximale de fichier de 100 Ko.

  - En cas de perte de la connectivité entre Lync Server et Exchange Server, c’est la photo basse résolution de l’utilisateur, **thumbnailPhoto**, issue des services de domaine Active Directory qui est affichée et ce, pour les utilisateurs internes uniquement.

  - Les photos d’utilisateur haute résolution sont affichées dans les réunions Lync 2013 lorsque la vidéo n’est pas activée pour un interlocuteur actif. De même, si vous passez la souris sur une miniature dans la galerie, la photo haute résolution s’affiche.

## Photos d’utilisateur dans Lync 2010

Dans le client Lync 2010, vous pouvez sélectionner l’une des deux options pour afficher une photo dans votre profil, **Image d’entreprise par défaut** et **Afficher une image à partir d’une adresse web**.

## Image d’entreprise par défaut

Quand vous sélectionnez l’option **Image d’entreprise par défaut**, Lync extrait la photo affichée à partir des services de domaine Active Directory. L’image utilisée est l’image définie comme valeur de l’attribut **thumbnailPhoto** dans services de domaine Active Directory. Il s’agit du même fichier utilisé par Exchange pour afficher les images dans Outlook.

Considérations relatives à l’utilisation d’images à partir des services de domaine Active Directory :

  - Seules les images dont la résolution ne dépasse pas 96 × 96 pixels sont prises en charge. La taille des fichiers image est limitée à 100 Ko.

  - Par défaut, les utilisateurs peuvent modifier l’image utilisée pour l’attribut **thumbnailPhoto**, mais pas directement par le biais du client Lync. Vous pouvez désactiver cette option via les services de domaine Active Directory.

  - Les images stockées dans les services de domaine Active Directory ne sont pas visibles par les contacts externes à votre organisation, même s’il s’agit de contacts fédérés.

  - Dans les grandes organisations, le stockage et l’extraction des images pour de nombreux utilisateurs peuvent avoir un impact sur la taille et les performances de la base de données des services de domaine Active Directory.

  - La limitation de la résolution et de la taille de fichier d’une image signifie que seules des images basse résolution peuvent être utilisées.

## Gestion des photos dans les services de domaine Active Directory par les utilisateurs

L’utilisateur ne peut pas modifier directement l’image utilisée dans son profil des services de domaine Active Directory par le biais du client Lync 2010. À cet effet, il peut utiliser l’une des options ci-dessous, le cas échéant :

  - **Serveur SharePoint** : les utilisateurs peuvent transférer une photo de « Mon site » vers un serveur SharePoint, puis [configurer la synchronisation de profil dans SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) pour synchroniser la photo avec l’attribut **thumbnailPhoto** dans les services de domaine Active Directory.

  - **Photo stockée à une URL accessible publiquement** : les utilisateurs peuvent configurer leur photo d’utilisateur en spécifiant une URL accessible publiquement pour l’image qu’ils souhaitent utiliser. L’image doit être accessible publiquement sans mot de passe. L’image stockée à l’adresse web spécifiée est transférée aux autres utilisateurs par le biais de la catégorie Carte de visite dans les informations de présence. Lorsque le client Lync doit afficher une photo d’utilisateur, il extrait l’image à partir de l’adresse web spécifiée.

  - **Applets de commande Exchange 2010 pour Windows PowerShell** : les administrateurs peuvent exécuter l’applet de commande [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) dans Exchange 2010 Management Shell pour gérer l’attribut **thumbnailPhoto**. Lorsque des images sont importées avec des applets de commande Exchange 2010, la taille du fichier est limitée à 10 Ko.

  - **Outils tiers** : les utilisateurs peuvent transférer leur propre photo pour l’attribut **thumbnailPhoto**.

## Afficher une photo à partir d’une adresse web

Lorsque vous sélectionnez l’option **Afficher une image à partir d’une adresse web**, Lync extrait l’image à l’adresse entrée et l’affiche pour votre photo d’utilisateur dans Lync.

Considérations relatives à l’utilisation d’images à partir d’une adresse web :

  - Les limites de taille de fichier sont déterminées par l’attribut **MaxPhotoSizeKB** dans la stratégie de client, définie avec l’applet de commande [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463). La limite de taille par défaut est de 30 Ko. La valeur maximale est de 100 Ko. Il n’y a pas de restriction sur la résolution de l’image, mais si vous essayez d’utiliser un fichier image dont la taille dépasse la limite, elle ne sera pas téléchargée dans les clients Lync. Vous pouvez définir la valeur sur 0 pour désactiver toutes les photos d’utilisateur afin qu’elles ne soient pas utilisées dans Lync.

  - Les photos d’utilisateur à partir d’une adresse web sont visibles par les contacts fédérés externes.

## Gestion des photos d’utilisateur avec des applets de commande de statégie de client

Dans Lync Server 2010, les paramètres de stratégie de client sont configurés avec les applets de commande CsClientPolicy. Les paramètres de stratégie configurés sont envoyés aux clients par le biais de la mise en service intrabande. Les deux paramètres des applets de commande CsClientPolicy qui déterminent l’expérience de la photo d’utilisateur sont **DisplayPhoto** et **MaxPhotoSizeKB**. Le paramètre de mise en service intrabande correspondant pour **DisplayPhoto** et **MaxPhotoSizeKB** est appelé **PhotoUsage**. Les valeurs du paramètre **PhotoUsage** sont envoyées aux clients par le biais de **endpointConfigurationprovisionGroup**. Pour plus d’informations, voir [Présentation des stratégies et des paramètres de client](http://go.microsoft.com/fwlink/?linkid=507470).

La valeur du paramètre **DisplayPhoto** détermine la source de l’image de la photo d’utilisateur. Les valeurs prises en charge figurent dans le tableau ci-dessous.


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
<th>Paramètres du client Lync 2010</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NoPhoto</p></td>
<td><p>Aucune</p></td>
<td><p><strong>Ne pas afficher mon image</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>Image d’entreprise par défaut</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>Adresse web</p></td>
<td><p><strong>Afficher une image à partir d’une adresse web</strong></p></td>
</tr>
</tbody>
</table>


## Comment le client Lync 2010 extrait les photos

Dans Lync 2010, les photos d’utilisateur sont gérées sur le serveur par le service de carnet d’adresses. Le client Lync extrait les photos d’utilisateur en interrogeant d’abord le service d’interrogation web de carnet d’adresses sur le serveur, qui est exposé par le biais du service web Distribution List Expansion. Le client reçoit le fichier image, puis le copie dans la mémoire cache de l’utilisateur pour éviter de télécharger l’image chaque fois qu’il doit l’afficher. Les valeurs d’attribut renvoyées par la requête sont également stockées dans l’entrée du service de carnet d’adresses mise en cache pour l’utilisateur. Toutes les 24 heures, ce service supprime toutes les images mises en cache, ce qui signifie que la mise à jour des nouvelles images de l’utilisateur dans la mémoire cache sur le serveur peut prendre 24 heures. Vous pouvez forcer la mise à jour dans la mémoire cache en utilisant l’applet de commande [Update-CsAddressBook](https://docs.microsoft.com/en-us/powershell/module/skype/Update-CsAddressBook).

Une valeur de hachage est également associée aux photos d’utilisateur figurant dans le statut de présence. Le client Lync l’utilise pour déterminer s’il existe une image plus récente disponible. Il est automatiquement averti des modifications apportées au fichier image dans le statut de présence.

> [!NOTE]  
> Comme les photos ne sont pas stockées dans la base de données GalContacts.db, le téléchargement des photos d’utilisateur ne dépend pas du paramètre <strong>AddressBookAvailability</strong> dans la stratégie de client (<a href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</a>).

La requête adressée au service d’interrogation web de carnet d’adresses inclut les attributs suivants :

  - **PhotoHash** : valeur de hachage des données de photo binaires, utilisée pour déterminer si la photo actuelle a été modifiée.

  - **PhotoRelPath** : chemin relatif du fichier image stocké sur le serveur.

  - **PhotoSize** : taille du fichier image, exprimée en octets.

  - **TimeStamp** : date et heure auxquelles le fichier image a été téléchargé sur le serveur pour la dernière fois et copié dans la mémoire cache du client.

Ensuite, après l’extraction du fichier image, le client Lync 2010 compare les valeurs d’attribut renvoyées par la requête à celles reçues par le client depuis la mise en service intrabande pour savoir si elles sont différentes. Si les valeurs sont différentes, le client extrait le fichier image de l’utilisateur connecté avec une demande HTTP GET.

De plus, le client vérifie auprès du serveur toutes les 24 heures dès lors que la version en cache du fichier image a été créée pour comparer la valeur de l’attribut **PhotoHash** sur le serveur avec la valeur sur le client. Si les valeurs sont différentes, le client sait que le fichier image a été modifié. Pour obtenir le fichier image mis à jour, le client interroge de nouveau le service d’interrogation web de carnet d’adresses pour mettre à jour le fichier image dans la mémoire cache du client avec le fichier image sur le serveur, ce qui réinitialise également l’attribut **TimeStamp** dans le fichier dans la mémoire cache du client.

Voici un exemple de réponse à une requête exécutée dans le service d’interrogation web de carnet d’adresses :

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

## Photos d’utilisateur dans Lync 2013

Lync 2013 a introduit la prise en charge des images haute résolution pour les photos d’utilisateur. Lync 2013 inclut également la prise en charge du stockage des photos d’utilisateur dans la boîte aux lettres de l’utilisateur dans Exchange 2013, qui élimine les limitations de la résolution et de la taille des images dans Lync 2010. Dans Lync 2013, les photos d’utilisateur peuvent posséder une résolution de 648 × 648 pixels et une taille maximale de 20 Mo. Dans Lync 2013, les photos haute résolution doivent se trouver dans la boîte aux lettres de l’utilisateur dans Exchange 2013 et ne sont prises en charge qu’avec le client Lync 2013. Cette intégration à Exchange tire parti de la nouvelle infrastructure d’autorisation incluse dans les versions 2013 de Lync, Exchange et SharePoint, appelée « Oauth ».

Si Exchange 2013 n’est pas utilisé dans votre déploiement, la prise en charge des photos d’utilisateur est identique à celle de Lync 2010. Cependant, les options utilisateur pour sélectionner la photo à utiliser sont différentes dans le client Lync 2013. Dans le client Lync 2013, les utilisateurs peuvent sélectionner **Masquer mon image** ou **Afficher mon image**. L’option **Afficher une image à partir d’un site web** n’est pas disponible par défaut, mais peut être activée en affectant une stratégie de client.

## Masquer mon image

Les paramètres des photos d’utilisateur se trouvent dans la boîte de dialogue **Options** dans Lync 2013. Lorsque vous sélectionnez **Masquer mon image**, aucune photo d’utilisateur n’est affichée dans le client Lync, mais votre photo reste affichée sur votre carte de visite et en dehors de Lync.

## Afficher mon image

Lorsque vous sélectionnez l’option **Afficher mon image**, votre photo d’utilisateur est affichée dans votre client Lync et pour les autres utilisateurs dans des conversations Lync. L’image utilisée est celle qui est stockée dans les services de domaine Active Directory.

## Afficher une image à partir d’un site web

L’option **Afficher une image à partir d’un site web** est disponible dans Lync 2013 une fois qu’une stratégie de client a été définie pour l’activer. La version du client doit être postérieure à la version 15.0.4535.1002, installée avec les [Mises à jour cumulatives Lync : novembre 2013](http://go.microsoft.com/fwlink/p/?linkid=509908). Les utilisateurs peuvent avoir besoin de se déconnecter et de se reconnecter pour voir les modifications dans le client.

Vous pouvez définir la stratégie de client de manière à activer le paramètre **Afficher une image à partir d’un site web** en exécutant la stratégie [Set-CsClientPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy) dans Lync Server Management Shell. Les exemples d’applets de commande ci-dessous montrent comment définir globalement la stratégie pour tous les utilisateurs inclus dans votre déploiement :

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

Lorsqu’une image est transférée dans la boîte aux lettres de l’utilisateur, Exchange crée automatiquement une version basse résolution de l’image, qui peut être utilisée dans des applications clientes. La photo de l’utilisateur est elle aussi mise à jour dans les services de domaine Active Directory.

> [!NOTE]  
> Lorsqu’un fichier image est mis à jour dans les services de domaine Active Directory, une image de 48 × 48 pixels y est créée et utilisée pour l’attribut thumbnailPhoto. Les éventuelles images existantes sont remplacées. Ainsi, si vous avez ajouté une image de 96 × 96 pixels aux services de domaine Active Directory, elle est remplacée par la nouvelle image de 48 × 48 pixels. Cela n’est important que si des utilisateurs inclus dans votre environnement utilisent des clients Lync 2010, car ces clients extraient les photos d’utilisateur à partir des services de domaine Active Directory. Vous pouvez importer des images de 96 × 96 pixels pour remplacer celles créées par les services de domaine Active Directory si votre organisation utilise des clients Lync 2010.

## Prise en charge des photos d’utilisateur dans Lync 2013

Dans Lync 2013, trois résolutions d’image sont prises en charge pour les photos d’utilisateur, comme indiqué dans le tableau ci-dessous. L’image utilisée est déterminée par le paramètre de stratégie de client affecté aux utilisateurs Lync. Pour plus d’informations, reportez-vous à la section « Gestion des photos d’utilisateur avec des applets de commande de stratégie de client » de cette rubrique.


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
<td><p>48 × 48</p></td>
<td><p>Utilisée si aucune image de résolution supérieure n’est sélectionnée</p></td>
</tr>
<tr class="even">
<td><p>96 × 96</p></td>
<td><p>Utilisée dans Outlook Web App et Outlook 2013</p></td>
</tr>
<tr class="odd">
<td><p>648 × 648</p></td>
<td><p>Utilisée dans le client de bureau Lync 2013 et Lync Web App 2013</p></td>
</tr>
</tbody>
</table>


Les utilisateurs avec une boîte aux lettres activée dans Exchange 2013 peuvent transférer une autre image, dont des photos haute résolution, par le biais des options du client Outlook Web Access ou Lync 2013. Les paramètres recommandés pour les images utilisées sont les suivants :

  - **Résolution d’image** : 648 × 648 pixels

  - **Intensité de couleurs** : 24 bits

  - **Taille des fichiers image** : jusqu’à 20 Mo

  - **Format de fichier** : JPEG

Une image JPEG 24 bits type d’une résolution de 648 × 648 pixels représente une taille de fichier d’environ 240 Ko, donc un espace de stockage de 1 Mo est nécessaire pour 4 photos d’utilisateur.

