---
title: 'Lync Server 2013 : mise à jour de la liste d’activation d’Outlook'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Updating the Outlook enable list
ms:assetid: 5db120dc-52f9-4dde-acb9-3824ae245086
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215438(v=OCS.15)
ms:contentKeyID: 48242739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7b4bc93f78ed72515270557e3224195df7ecd81
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="updating-the-outlook-enable-list-in-lync-server-2013"></a>Mise à jour de la liste d’activation d’Outlook dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-01-07_

Vous pouvez vous assurer que le complément de réunion en ligne pour Microsoft Lync 2013 reste toujours activé pour les utilisateurs en créant une stratégie qui l’inclut dans la liste de gestion des compléments pour Outlook. La stratégie liste de gestion des compléments est incluse dans les fichiers de modèle d’administration Office pour la console de gestion des stratégies de groupe. Il crée une clé de Registre sous\\les\\stratégies\\de\\logiciel\\HKCU\\Microsoft\\Office 15,0\\Outlook15 Resilience AddinList. Vous pouvez ajouter une valeur pour ucaddin. dll à cette clé et configurer la valeur de ucaddin. dll de sorte qu’elle soit toujours activée et que les utilisateurs ne puissent pas la désactiver manuellement.

<div>

## <a name="to-add-ucaddindll-to-the-outlook-add-in-list"></a>Pour ajouter ucaddin. dll à la liste des compléments Outlook

  - Dans la clé de Registre AddinList, située sous\\stratégies\\\\logicielles\\HKCU\\Microsoft\\Office\\15,0 Outlook15\\de résilience AddinList, ajoutez la valeur suivante :
    
      - Type de Registre =\_reg SZ
    
      - Nom = ucaddin. dll
    
      - Valeur = 1 (indique que le complément est toujours activé et qu’il ne peut pas être géré par l’utilisateur final)

</div>

</div>

<span> </span>

</div>

</div>

</div>

