---
title: "Conf. de l’util. de photos haute résolution dans Microsoft Lync Server 2013"
TOCtitle: "Conf. de l’util. de photos haute résolution dans Microsoft Lync Server 2013"
ms:assetid: 995da78a-dc44-45a3-908d-16fe36cfa0d9
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ688150(v=OCS.15)
ms:contentKeyID: 49891457
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de l’utilisation de photos haute résolution dans Microsoft Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

Microsoft Lync Server 2010 offrait aux utilisateurs la possibilité d’afficher des photos de leurs contacts (et de rendre leurs propres photos accessibles à d’autres personnes). En général, ces photos étaient stockées dans le cadre de l’attribut thumbnailPhoto de l’utilisateur dans Active Directory. Ceci imposait une sérieuse limitation quant à la taille et la résolution des photos ; en effet, l’attribut thumbnailPhoto ne peut pas contenir de photographie dont la taille dépasse 48 x 48 pixels.

En revanche, dans Microsoft Lync Server 2013 les photos peuvent être stockées dans la boîte aux lettres Microsoft Exchange Server 2013 d’un utilisateur, ce qui permet d’utiliser des photos d’une taille maximale de 648 x 648 pixels. De plus, Exchange 2013 peut si besoin est redimensionner automatiquement ces photos pour une utilisation dans différents produits. Cela donne généralement trois tailles et résolutions de photos différentes :

  - 48 x 48 pixels, la taille utilisée pour l’attribut thumbnailPhoto Active Directory. Si vous téléchargez une photo vers Exchange 2013, Exchange crée automatiquement une version de 48 x 48 pixels de cette photo et met à jour l’attribut thumbnailPhoto de l’utilisateur. Notez toutefois que ce n’est pas le cas dans le sens inverse : si vous mettez manuellement à jour l’attribut thumbnailPhoto dans Active Directory, la photo stockée dans la boîte aux lettres Exchange 2013 de l’utilisateur n’est pas mise à jour automatiquement.

  - 96 x 96 pixels, pour une utilisation dans Microsoft Outlook 2013 Web App, Microsoft Outlook 2013, Microsoft Lync Web App et Lync 2013.

  - 648 x 648 pixels, pour une utilisation dans Lync 2013 et Microsoft Lync Web App.

> [!NOTE]  
> Si vous disposez des ressources nécessaires, nous vous recommandons de télécharger des photos de 648 x 648 pixels. Cela permet de bénéficier de la résolution maximale et d’une qualité d’image optimale dans toutes les applications Office 2013. Chaque photo JPEG de 648 x 648 pixels et d’une profondeur de 24 bits équivaut à une taille de fichier d’environ 240 kilo-octets, ce qui signifie que vous avez besoin d’environ 1 mégaoctet d’espace disque pour quatre photos d’utilisateurs.

Les photos haute résolution, qui sont accessibles par le biais des services web Exchange, peuvent être téléchargées par les utilisateurs qui exécutent Outlook 2013 Web App. Les utilisateurs ne peuvent mettre à jour que leur propre photo : les administrateurs, quant à eux, peuvent mettre à jour la photo de tout utilisateur à l’aide d’Exchange Management Shell et d’une série de commandes Windows PowerShell semblable à la suivante :

    $photo = ([Byte[]] $(Get-Content -Path "C:\Photos\Kenmyer.jpg" -Encoding Byte -ReadCount 0))
    Set-UserPhoto -Identity "Ken Myer" -PictureData $photo -Confirm:$False
    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

La première commande de l’exemple ci-dessus utilise l’applet de commande Get-Content pour lire le contenu du fichier C:\\Photos\\Kenmyer.jpg et stocker les données dans une variable nommée $photo. Dans la seconde commande, l’applet de commande Exchange Set-UserPhoto est utilisée pour télécharger la photo et l’associer au compte d’utilisateur de Ken Myer.

> [!NOTE]  
> Dans cet exemple, le nom complet Active Directory de Ken Myer est utilisé comme identité de compte d’utilisateur. Vous pouvez également faire référence à un compte d’utilisateur au moyen d’autres identificateurs tels que l’adresse SMTP de l’utilisateur ou son nom d’utilisateur principal. Pour plus d’informations, voir la documentation de l’applet de commande Set-UserPhoto à l’adresse <a href="http://go.microsoft.com/fwlink/?linkid=268536%26clcid=0x40c">http://go.microsoft.com/fwlink/?linkid=268536&amp;clcid=0x40C</a>.

Télécharger la photo n’équivaut pas à l’assigner au compte d’utilisateur de Ken Myer. Cela entraîne simplement l’affichage d’un aperçu de cette photo dans la page Options d’Outlook Web App. Pour assigner cette photo au compte d’utilisateur, celui-ci doit cliquer sur **Enregistrer** dans la page Options ou l’administrateur doit exécuter la troisième commande de l’exemple. Cette troisième commande utilise le paramètre Save pour assigner la photo au compte d’utilisateur de Ken Myer :

    Set-UserPhoto -Identity "Ken Myer" -Save -Confirm:$False

Pour vérifier que la nouvelle photo a été assignée au compte d’utilisateur, Ken Myer peut se connecter à Lync 2013, sélectionner **Options**, puis **Mon image**. La photo nouvellement téléchargée doit alors s’afficher comme photo personnelle de Ken. En guise d’alternative, les administrateurs peuvent vérifier la photo de tout utilisateur en démarrant Internet Explorer et en accédant à une URL semblable à la suivante :

    https://atl-mail-001.litwareinc.com/ews/Exchange.asmx/s/GetUserPhoto?email=kenmyer@litwareinc.com&size=HR648x648

Si l’administrateur peut afficher la photo à l’aide d’Internet Explorer mais que l’utilisateur ne peut pas voir sa propre photo dans Lync 2013, cela signifie en général qu’il existe un problème de connectivité au niveau des services web Exchange ou du service de découverte automatique Exchange.

Notez également qu'aucune configuration supplémentaire n'est nécessaire pour rendre cette photo disponible dans Lync 2013. À la place, la photo sera instantanément disponible une fois qu'elle a été téléchargée et que l'applet de commande Set-UserPhoto a été exécuté.

