---
title: 'Lync Server 2013 : vérification de la réplication de schéma'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verifying schema replication
ms:assetid: ad01a7cf-aa79-4648-ba5a-a7a09172db36
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412822(v=OCS.15)
ms:contentKeyID: 48185124
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 41cb48da1711cfa6eb29a90f19a9b6e42b110c52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007293"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Vérification de la réplication de schéma Active Directory dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

Avant d’exécuter la préparation de la forêt, vérifiez manuellement que la partition de schéma a été répliquée.

<div>

## <a name="to-manually-verify-schema-replication"></a>Pour vérifier manuellement la réplication de schéma

1.  Ouvrez une session sur un contrôleur de domaine en tant que membre du groupe Administrateurs d’entreprise.

2.  Ouvrez l’éditeur ADSI en cliquant sur **Démarrer**, sur **Outils d’administration**, puis sur **Modification ADSI**.
    
    <div>
    

    > [!TIP]  
    > Vous pouvez également exécuter <STRONG>adsiedit.msc</STRONG> à partir de la ligne de commande.

    
    </div>

3.  Dans l’arborescence de Microsoft Management Console (MMC), cliquez sur **Modification ADSI** si cette option n’a pas encore été sélectionnée.

4.  Dans le menu **Action**, cliquez sur **Se connecter à**.

5.  Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.

6.  Sous le conteneur de schéma, recherchez CN=ms-RTC-SIP-SchemaVersion. Si cet objet existe et si la valeur de l’attribut **rangeUpper** est 1150 et si la valeur de l’attribut **rangeLower** est 3, cela signifie que le schéma a été mis à jour et répliqué avec succès. Si cet objet n’existe pas ou si la valeur des attributs **rangeUpper** et **rangeLower** n’est pas spécifiée, cela signifie que le schéma n’a pas été modifié ou n’a pas été répliqué.

</div>

<div>

## <a name="see-also"></a>Voir aussi


[Exécution de la préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-running-schema-preparation.md)  


[Préparation du schéma Active Directory dans Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

