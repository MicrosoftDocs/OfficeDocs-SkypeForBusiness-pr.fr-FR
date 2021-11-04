---
title: Planifier le contrôle d’appel distant dans Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Le contrôle d’appel distant était une fonctionnalité des versions précédentes de Lync Server qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype Entreprise Server, cette fonctionnalité a été remplacée par Appel via le travail. Dans les versions du client pour Skype Entreprise Server 2015 et à l’avenir, le contrôle d’appel distant n’est plus disponible pour la configuration dans le client et a été supprimé pour utilisation.
ms.openlocfilehash: 23d8f25f4a416c10bf4fd186db68a729703891ca
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746740"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a>Planifier le contrôle d’appel distant dans Skype Entreprise
 
Le contrôle d’appel distant était une fonctionnalité des versions précédentes de Lync Server qui permettait aux utilisateurs de contrôler leurs téléphones PBX avec Lync Server. Dans Skype Entreprise Server, cette fonctionnalité a été remplacée par Appel via le travail.  *Dans les versions du client pour Skype Entreprise Server 2015 et à l’avenir, le contrôle d’appel distant n’est plus disponible pour la configuration dans le client et a été supprimé pour utilisation.* 
  
 Les utilisateurs du contrôle d’appel distant de votre organisation qui sont situés sur des serveurs frontaux exécutant Lync Server peuvent continuer à utiliser le contrôle d’appel distant, même s’ils utilisent un client Skype Entreprise client. Toutefois, pour tous les utilisateurs Skype Entreprise Server, le contrôle d’appel distant n’est pas pris en charge. Consultez le tableau suivant pour les combinaisons serveur/client et pour savoir si elles peuvent prendre en charge le contrôle d’appel distant ou l’appel via le travail.
  
|&nbsp;|Skype Entreprise Client avec Skype’interface utilisateur activée|Skype Entreprise Client avec l’interface utilisateur Lync activée|Skype Entreprise client 2016|Lync 2013 Client|Client Lync 2010|
|:-----|:-----|:-----|:-----|:-----|:-----|
| Skype Entreprise Server  |Appel via le travail   |1  |Appel via le travail   |1  |1  |
| Lync Server 2013  |Contrôle d’appel distant   |Contrôle d’appel distant   |1  |Contrôle d’appel distant   |Contrôle d’appel distant   |
| Lync Server 2010  |Contrôle d’appel distant   |Contrôle d’appel distant   |1  |Contrôle d’appel distant   |Contrôle d’appel distant   |
   
1. Aucune des fonctionnalités n’est prise en charge.
  
Pour plus d’informations, [voir Remote Call Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) dans la documentation Lync Server 2013.
  
## <a name="see-also"></a>Voir aussi

[Planifier l’appel via le Skype Entreprise Server](call-via-work.md)
  
[Comparaison des fonctionnalités du client de bureau pour Skype Entreprise](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[Effectuer un appel Skype Entreprise téléphone de bureau PBX pour l’audio](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)