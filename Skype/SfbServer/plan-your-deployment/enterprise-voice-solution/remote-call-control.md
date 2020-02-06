---
title: Planifier le contrôle d’appel distant dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Le contrôle d’appel distant était une fonctionnalité des versions précédentes de Lync Server, qui permettaient aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype entreprise Server, cette fonction a été remplacée par un appel via le travail. Dans les versions de client de Skype entreprise Server 2015 et en passant à la reprise, le contrôle d’appel distant n’est plus disponible dans le client et a été supprimé pour une utilisation.
ms.openlocfilehash: 67010a0bc74ef46dcf204e3b2a905be87c182daf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802504"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Planifier le contrôle d’appel distant dans Skype entreprise
 
Le contrôle d’appel distant était une fonctionnalité des versions précédentes de Lync Server, qui permettaient aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype entreprise Server, cette fonction a été remplacée par un appel via le travail.  *Dans les versions de client de Skype entreprise Server 2015 et en passant à la reprise, le contrôle d’appel distant n’est plus disponible dans le client et a été supprimé pour une utilisation.* 
  
 Contrôle d’appel distant les utilisateurs de votre organisation qui résident sur des serveurs frontaux exécutant Lync Server peuvent continuer à utiliser le contrôle d’appel distant, même s’ils utilisent un client Skype entreprise. Toutefois, pour les utilisateurs hébergés sur Skype entreprise Server, le contrôle d’appel distant n’est pas pris en charge. Consultez le tableau suivant pour les combinaisons serveur/client et pour savoir si elles peuvent prendre en charge le contrôle d’appel distant ou un appel via le bureau.
  
||**Client Skype entreprise avec interface utilisateur Skype activée**|**Client Skype entreprise avec interface utilisateur Lync activée**|**Client 2016 Skype entreprise**|**Client 2013 Lync**|**Client Lync 2010**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype entreprise Server <br/> |Appel via le bureau  <br/> |1 <br/> |Appel via le bureau  <br/> |1 <br/> |1 <br/> |
| Lync Server 2013 <br/> |Contrôle d’appel distant  <br/> |Contrôle d’appel distant  <br/> |1 <br/> |Contrôle d’appel distant  <br/> |Contrôle d’appel distant  <br/> |
| Lync Server 2010 <br/> |Contrôle d’appel distant  <br/> |Contrôle d’appel distant  <br/> |1 <br/> |Contrôle d’appel distant  <br/> |Contrôle d’appel distant  <br/> |
   
1. Aucune de ces fonctionnalités n’est prise en charge.
  
Pour plus d’informations, reportez-vous à [contrôle d’appel distant](https://go.microsoft.com/fwlink/p/?LinkId=530208) dans la documentation de Lync Server 2013.
  
## <a name="see-also"></a>Voir aussi

[Planifier un appel via le travail dans Skype entreprise Server](call-via-work.md)
  
[Comparaison des fonctionnalités des clients de bureau pour Skype Entreprise](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Passer un appel Skype entreprise en utilisant votre téléphone de bureau PBX pour le son](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

