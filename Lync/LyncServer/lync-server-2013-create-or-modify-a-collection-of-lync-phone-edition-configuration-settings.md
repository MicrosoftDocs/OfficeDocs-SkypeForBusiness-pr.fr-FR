---
title: Création ou modification d’une collection de paramètres de configuration de Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 23248517bc0bba55c600e732c0a7edb96f468713
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035570"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Création ou modification d’une collection de paramètres de configuration Lync Phone Edition dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-23_

Lorsque vous installez Lync Server, vous obtenez une collection globale de paramètres Lync Phone Edition. Ces paramètres s’appliquent à tous les appareils exécutant Lync Phone Edition dans votre déploiement. Vous pouvez modifier ces paramètres à tout moment. Vous pouvez également configurer une nouvelle collection de paramètres qui s’applique aux appareils d’un site spécifique. Les paramètres du site prévalent sur les paramètres globaux.

Les paramètres de configuration comprennent le nom de la collection, l’étendue (globale ou site), le paramètre de sécurité SIP, le niveau de journalisation, le niveau de qualité de service de la voix (QoS), le paramètre de verrouillage du téléphone et les détails du verrouillage du téléphone, c’est-à-dire a) la longueur requise du code confidentiel de déverrouillage et b) le délai d’inactivité du téléphone avant son propre verrouillage.

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>Pour créer une collection de paramètres de configuration de Lync Phone Edition ou modifier les paramètres d’une collection existante

1.  Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Panneau de configuration Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **Clients**, puis sur le bouton de navigation **Configuration du périphérique**.

4.  Dans la page **Configuration du périphérique**, effectuez l’une des opérations suivantes :
    
      - Pour créer une nouvelle collection de paramètres de configuration de Lync Phone Edition, cliquez sur **nouveau**, sélectionnez un site, cliquez sur **OK**, vérifiez les paramètres par défaut et, si vous le souhaitez, effectuez les modifications nécessaires.
    
      - Pour modifier l’un des paramètres d’une collection existante, cliquez sur la collection, cliquez sur le menu **Modifier**, cliquez sur **Afficher les détails**, puis apportez vos modifications.
        
        <div>
        

        > [!TIP]
        > Pour revenir à l’utilisation des paramètres par défaut de la collection globale, cliquez sur la collection globale, cliquez sur le menu <STRONG>Modifier</STRONG>, cliquez sur <STRONG>Supprimer</STRONG>, puis sur <STRONG>OK</STRONG>. Cela ne supprime pas la collection globale, mais rétablit simplement les paramètres à leurs valeurs par défaut.

        
        </div>

5.  Cliquez sur **Valider**.

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Création de nouveaux paramètres de configuration de Lync Phone Edition à l’aide d’applets de commande Windows PowerShell

Vous pouvez créer des paramètres de configuration de Lync Phone Edition (au niveau de l’étendue site uniquement) à l’aide de Windows PowerShell et de la cmdlet **New-CsUCPhoneConfiguration** . Vous pouvez exécuter cette applet de commande à partir de Lync Server 2013 Management Shell ou d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell à distance pour se connecter à Lync Server, voir l’article du blog Lync Server Windows PowerShell « Quick Start : Managing Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 Using Remote PowerShell » (en anglais) à l’adresse.

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>Pour créer de nouveaux paramètres de configuration de Lync Phone Edition qui utilisent les valeurs par défaut

  - Cette commande permet de créer un jeu de paramètres de configuration de téléphonie UC pour le site Redmond :
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Étant donné qu’aucun paramètre (autre que le paramètre Identity obligatoire) n’a été spécifié dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>Pour modifier une seule valeur de propriété lors de la création de nouveaux paramètres de configuration de Lync Phone Edition

  - Pour créer des paramètres qui utilisent des valeurs de propriété différentes, il suffit d’inclure le paramètre et la valeur de paramètre appropriés. Par exemple, pour créer une collection de paramètres de configuration de téléphonie UC qui, par défaut, exige le verrouillage du téléphone, utilisez une commande comme celle-ci :
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>Pour modifier plusieurs valeurs de propriété lors de la création de nouveaux paramètres de configuration de Lync Phone Edition

  - Il est possible de modifier plusieurs valeurs de propriété en incluant plusieurs paramètres. Par exemple, cette commande permet de mettre en application le verrouillage du téléphone et également de définir une longueur minimale de 8 chiffres pour le code confidentiel :
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

Pour plus d’informations, consultez la rubrique [New-CsUCPhoneConfiguration](https://technet.microsoft.com/library/Gg398445(v=OCS.15)).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Supprimer une collection existante de paramètres de configuration Lync Phone Edition dans Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Configurer les paramètres de sécurité pour Lync Phone Edition dans Lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Appliquer le verrouillage du téléphone dans Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

