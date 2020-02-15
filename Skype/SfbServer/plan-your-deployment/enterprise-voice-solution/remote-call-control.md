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
description: Le contrôle d’appel distant était une fonctionnalité dans les versions précédentes de Lync Server, qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype entreprise Server, cette fonctionnalité a été remplacée par l’appel via le bureau. Dans les versions client pour Skype entreprise Server 2015 et en aval, le contrôle d’appel distant n’est plus disponible à configurer dans le client et a été supprimé pour être utilisé.
ms.openlocfilehash: 788939c392b1d86d14590232c19979e664fa0c09
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982799"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Planifier le contrôle d’appel distant dans Skype entreprise
 
Le contrôle d’appel distant était une fonctionnalité dans les versions précédentes de Lync Server, qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype entreprise Server, cette fonctionnalité a été remplacée par l’appel via le bureau.  *Dans les versions client pour Skype entreprise Server 2015 et en aval, le contrôle d’appel distant n’est plus disponible à configurer dans le client et a été supprimé pour être utilisé.* 
  
 Contrôle d’appel distant les utilisateurs de votre organisation qui sont hébergés sur des serveurs frontaux exécutant Lync Server peuvent continuer à utiliser le contrôle d’appel distant, même s’ils utilisent un client Skype entreprise. Toutefois, pour tous les utilisateurs hébergés sur Skype entreprise Server, le contrôle d’appel distant n’est pas pris en charge. Consultez le tableau suivant pour les combinaisons serveur/client et s’ils peuvent prendre en charge le contrôle d’appel distant ou l’appel via le bureau.
  
||**Client Skype entreprise avec interface utilisateur Skype activée**|**Client Skype entreprise avec interface utilisateur Lync activée**|**Client Skype entreprise 2016**|**Client Lync 2013**|**Client Lync 2010**|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype Entreprise Server <br/> |Appel via le Bureau  <br/> |1  <br/> |Appel via le Bureau  <br/> |1  <br/> |1  <br/> |
| Lync Server 2013 <br/> |Contrôle d’appel distant  <br/> |Contrôle d’appel distant  <br/> |1  <br/> |Contrôle d’appel distant  <br/> |Contrôle d’appel distant  <br/> |
| Lync Server 2010 <br/> |Contrôle d’appel distant  <br/> |Contrôle d’appel distant  <br/> |1  <br/> |Contrôle d’appel distant  <br/> |Contrôle d’appel distant  <br/> |
   
1. Aucune des fonctionnalités n’est prise en charge.
  
Pour plus d’informations, reportez-vous à [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) dans la documentation Lync Server 2013.
  
## <a name="see-also"></a>Voir aussi

[Planifier l’appel via le bureau dans Skype entreprise Server](call-via-work.md)
  
[Comparaison des fonctionnalités des clients de bureau pour Skype entreprise](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Passer un appel Skype entreprise mais utiliser votre téléphone de bureau PBX pour l’audio](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

