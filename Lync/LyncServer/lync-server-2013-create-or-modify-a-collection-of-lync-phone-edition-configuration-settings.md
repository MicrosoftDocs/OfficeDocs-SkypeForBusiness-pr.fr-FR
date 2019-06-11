---
title: Créer ou modifier un ensemble de paramètres de configuration de Lync Phone Edition
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a collection of Lync Phone Edition configuration settings
ms:assetid: 6cf714af-8f57-4a71-89ad-0a776302b2ba
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688086(v=OCS.15)
ms:contentKeyID: 49733683
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f3012ffeeb8dd4559ee05a45dd07becefd099691
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831816"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-collection-of-lync-phone-edition-configuration-settings-in-lync-server-2013"></a>Créer ou modifier un ensemble de paramètres de configuration de Lync Phone Edition dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-23_

Lorsque vous installez Lync Server, vous obtenez une collection globale de paramètres Lync Phone Edition. Ces paramètres s’appliquent à tous les appareils exécutant Lync Phone Edition dans votre déploiement. Vous pouvez modifier ces paramètres à tout moment. Vous pouvez également définir une nouvelle collection de paramètres qui s’appliquent aux appareils d’un site spécifique. Les paramètres de site sont prioritaires par rapport aux paramètres globaux.

Les paramètres de configuration comprennent le nom de la collection, l’étendue (globale ou le site), le paramètre de sécurité SIP, le niveau de journalisation, le niveau de qualité de service (QoS), le paramètre de verrouillage du téléphone et les détails du verrouillage du téléphone, c’est-à-dire le nombre de fois qu’un numéro d’identification personnelle est déverrouillé ( Code confidentiel) doit comporter et b) le téléphone reste inactif avant de se bloquer.

<div>

## <a name="to-create-a-collection-of-lync-phone-edition-configuration-settings-or-edit-settings-for-an-existing-collection"></a>Pour créer une collection de paramètres de configuration de Lync Phone Edition ou des paramètres d’édition pour une collection existante

1.  À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.

2.  Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le panneau de configuration de Lync Server. Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration de Lync Server, voir [ouvrir les outils d’administration de Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Dans la barre de navigation de gauche, cliquez sur **clients**, puis sur le bouton navigation de **configuration d’appareil** .

4.  Dans la page Configuration de l' **appareil** , effectuez l’une des opérations suivantes:
    
      - Pour créer une nouvelle collection de paramètres de configuration de Lync Phone Edition, cliquez sur **nouveau**, sélectionnez un site, cliquez sur **OK**, passez en revue les paramètres par défaut et, si vous le souhaitez, apportez les modifications souhaitées.
    
      - Pour modifier l’un des paramètres d’une collection existante, cliquez dessus, cliquez sur le menu **édition** , cliquez sur **afficher les détails**, puis apportez les modifications souhaitées.
        
        <div>
        

        > [!TIP]
        > Pour revenir à l’utilisation des paramètres par défaut pour la collection globale, cliquez sur la collection globale, cliquez sur le menu <STRONG>Edition</STRONG> , cliquez sur <STRONG>supprimer</STRONG>, puis cliquez sur <STRONG>OK</STRONG>. Cette opération n’entraîne pas la suppression de la collection globale. elle réinitialise uniquement les paramètres aux valeurs par défaut.

        
        </div>

5.  Cliquez sur **Valider**.

</div>

<div>

## <a name="creating-new-lync-phone-edition-configuration-settings-by-using-windows-powershell-cmdlets"></a>Création de nouveaux paramètres de configuration de Lync Phone Edition à l’aide d’applets de cmdlet Windows PowerShell

Vous pouvez créer des paramètres de configuration de Lync Phone Edition (à l’étendue du site uniquement) à l’aide de Windows PowerShell et de l’applet **de nouvelle cmdlet New-CsUCPhoneConfiguration** . Vous pouvez exécuter cette applet de commande sur Lync Server 2013 Management Shell ou à partir d’une session distante de Windows PowerShell. Pour plus d’informations sur l’utilisation de Windows PowerShell distant pour vous connecter à Lync Server, voir l’article de blog Lync Server Windows PowerShell «démarrage rapide: gestion de Microsoft Lync [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Server 2010 à l’aide de Remote PowerShell».

<div>

## <a name="to-create-new-lync-phone-edition-configuration-settings-that-use-the-default-values"></a>Pour créer des paramètres de configuration de Lync Phone Edition utilisant les valeurs par défaut

  - Cette commande crée un ensemble de paramètres de configuration de téléphone de UC pour le site de Redmond:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond"
    
    Comme aucun paramètre (autre que celui obligatoire sur l’identité) n’a été précisé dans la commande précédente, la nouvelle collection de paramètres de configuration utilise les valeurs par défaut pour toutes ses propriétés.

</div>

<div>

## <a name="to-change-a-single-property-value-when-creating-new-lync-phone-edition-configuration-settings"></a>Pour modifier une valeur de propriété unique lors de la création de nouveaux paramètres de configuration de Lync Phone Edition

  - Pour créer des paramètres qui font appel à d’autres valeurs de propriétés, incluez simplement le paramètre approprié et sa valeur. Par exemple, pour créer un ensemble de paramètres de configuration de téléphone de type UC qui, par défaut, nécessite le verrouillage du téléphone, utilisez une commande comme celle-ci:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True

</div>

<div>

## <a name="to-change-multiple-property-values-when-creating-new-lync-phone-edition-configuration-settings"></a>Pour modifier plusieurs valeurs de propriétés lors de la création de nouveaux paramètres de configuration de Lync Phone Edition

  - Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande applique le verrouillage du téléphone et définit la longueur minimale du code confidentiel sur 8 chiffres:
    
        New-CsUCPhoneConfiguration -Identity "site:Redmond" -EnforcePhoneLock $True -MinPhonePinLength 8

</div>

Pour plus d’informations, consultez la rubrique [New-CsUCPhoneConfiguration](https://technet.microsoft.com/en-us/library/Gg398445(v=OCS.15)).

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Supprimer une collection existante de paramètres de configuration de Lync Phone Edition dans Lync Server 2013](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[Configurer les paramètres de sécurité de Lync Phone Edition dans Lync Server 2013](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[Renforcer le verrouillage du téléphone dans Lync Server 2013](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

