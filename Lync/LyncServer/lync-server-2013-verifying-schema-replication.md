---
title: 'Lync Server 2013 : Vérification de la réplication de schéma'
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
ms.openlocfilehash: e7ea90012c116bb66caf16313d930c6f05db4413
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742094"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verifying-active-directory-schema-replication-in-lync-server-2013"></a>Vérification de la réplication de schéma Active Directory dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

Avant de procéder à la préparation de la forêt, vérifiez manuellement que celle-ci a été répliquée.

<div>

## <a name="to-manually-verify-schema-replication"></a>Pour vérifier manuellement la réplication de schéma

1.  Ouvrez une session sur un contrôleur de domaine en tant que membre du groupe administrateurs d’entreprise.

2.  Ouvrez ADSI Edit en cliquant sur **Démarrer**, sur **Outils d’administration**, puis sur **modification ADSI**.
    
    <div>
    

    > [!TIP]  
    > Vous pouvez également exécuter <STRONG>adsied. msc</STRONG> à partir de la ligne de commande.

    
    </div>

3.  Dans l’arborescence Microsoft Management Console (MMC), si ce n’est pas déjà fait, cliquez sur **ADSI Edit**.

4.  Dans le menu **Action**, cliquez sur **Connexion**.

5.  Dans la boîte de dialogue **Paramètres de connexion** sous **Sélectionnez un contexte d’attribution de noms connu**, sélectionnez **Schéma**, puis cliquez sur **OK**.

6.  Sous le conteneur de schéma, recherchez CN=ms-RTC-SIP-SchemaVersion. Si cet objet existe et que la valeur de l’attribut **rangeUpper** est 1150 et que la valeur de l’attribut **rangeLower** est 3, le schéma a été correctement mis à jour et répliqué. Si cet objet n’existe pas ou si les valeurs des attributs **rangeUpper** et **rangeLower** ne sont pas spécifiées, le schéma n’a pas été modifié ou n’a pas été répliqué.

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

