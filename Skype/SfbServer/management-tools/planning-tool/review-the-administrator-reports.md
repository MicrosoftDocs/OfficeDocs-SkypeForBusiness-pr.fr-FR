---
title: Examiner les rapports de l’administrateur Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 4/5/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 22d480ea-cd64-4d09-99fe-96e997570844
description: Les rapports de l’administrateur contiennent des informations détaillées sur le déploiement et les opérations. Les rapports sont générés en fonction des sélections marquées dans les sites de conception. Le concepteur peut compléter les rapports de l’administrateur en modifiant les diagrammes des réseaux et en définissant les adresses IP complètes et les noms de domaine complets (FQDN) pour les serveurs, les pools et les programmes d’équilibrage de charge.
ms.openlocfilehash: fd48494a603b6e279790a92e38040c3e26b01668
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845297"
---
# <a name="review-the-administrator-reports-in-skype-for-business-server-2015"></a>Examiner les rapports de l’administrateur Skype Entreprise Server 2015

Les rapports de l’administrateur contiennent des informations détaillées sur le déploiement et les opérations. Les rapports sont générés en fonction des sélections marquées dans les **sites de conception.** Le concepteur peut compléter les rapports de l’administrateur en modifiant les diagrammes des réseaux et en définissant les adresses IP complètes et les noms de domaine complets (FQDN) pour les serveurs, les pools et les programmes d’équilibrage de charge.

La fonctionnalité Rapports de l’administrateur vous permet de :

- [Consulter le rapport de synthèse](review-the-administrator-reports.md#Summary_report)

- [Examiner le rapport certificats](review-the-administrator-reports.md#Certificates_Report)

- [Consulter le rapport de pare-feu](review-the-administrator-reports.md#Firewall_report)

- [Consulter le rapport DNS](review-the-administrator-reports.md#DNS_Report)

## <a name="review-the-summary-report"></a>Consulter le rapport de synthèse
<a name="Summary_report"> </a>

Le rapport Skype Entreprise’administrateur général est le premier des quatre rapports précieux qui documentent en détail votre conception. Les informations de ce rapport, ainsi que les trois autres rapports associés, sont utiles pour votre Teams :

![Rapport d’administration récapitulatif général.](../../media/General_Summary_Report_Admin_Report.png)

Le rapport récapitulatif répertorie des informations de configuration générales relatives à votre réseau de périmètre. L’emplacement, le nom de domaine complet (FQDN) et l’adresse IP, le type de réseau et les commentaires spécifiques à un rôle donné sont documentés.

Le concepteur et chacune des équipes qui déploient, gèrent et gèrent l’infrastructure doivent examiner le rapport récapitulatif pour plus de précision et s’assurer que les erreurs sont au minimum.

Vous pouvez également afficher des rapports plus détaillés :

- Rapport des certificats

- Rapport du pare-feu

- Rapport DNS

## <a name="review-the-certificates-report"></a>Consulter le rapport certificats
<a name="Certificates_Report"> </a>

Le rapport des certificats contient tous les certificats requis dans le déploiement Skype Entreprise Server 2015. L’outil de planification compte les noms du sujet et les autres noms du sujet entrés. Le texte par défaut qui n’est pas mis à jour peut représenter un défi potentiel pour l’équipe responsable de la demande et de l’émission des certificats. Les informations de certificat contiennent également des données sur l’emplacement à partir duquel le certificat peut généralement être émis. Si l’infrastructure ne dispose pas d’une PKI interne, tous les certificats peuvent être demandés par l’intermédiaire d’un fournisseur de certificats public. Les champs EKU et Affecter à du rapport sont très utiles pour connaître ce que doivent être l’objectif et l’emplacement de chaque certificat.

![Rapport d’administration des certificats.](../../media/Certificates_Report_Admin_Report.png)

Examinez attentivement et assurez-vous de bien comprendre l’utilisation et l’objectif de chaque certificat dans le déploiement. S’il existe une question sur l’objectif d’un certificat, déterminez le serveur ou le service avec lequel il s’agit. Les certificats Skype Entreprise Server 2015 sont utilisés à deux fins principales :

- Mutual Transport Layer Security (MTLS) : les ordinateurs impliqués dans la communication présentent chacun un certificat qui prouve leur identité à un autre ordinateur. C’est ce qu’on appelle l’authentification de serveur. La communication ne peut pas commencer tant que chaque ordinateur n’a pas confiance en l’identité de l’autre ordinateur.

- Chiffrement : le chiffrement (Secure Sockets Layer, ou SSL, et Transport Layer Security, ou TLS) est un moyen essentiel pour sécuriser les communications, garantir la confidentialité et créer un système de communication et de collaboration approuvé.

## <a name="review-the-firewall-report"></a>Consulter le rapport de pare-feu
<a name="Firewall_report"> </a>

Skype Entreprise Server 2015 possède un ensemble potentiellement complexe de règles de pare-feu. L’outil de planification réduit cette complexité en générant un rapport qui définit en détail toutes les exigences de pare-feu, en fonction des critères d’entrée du concepteur. L’administrateur du pare-feu informatique pourra utiliser ce rapport pour configurer et définir les règles nécessaires.

Du point de vue de la gestion du pare-feu, le rapport doit être soigneusement examiné pour s’assurer qu’il n’existe aucun conflit avec les règles de pare-feu sortantes et qu’aucune stratégie ou procédure ne peut être enfreinte.

![Rapport d’administration du pare-feu.](../../media/Firewall_Report_Admin_Report.png)

## <a name="review-the-dns-report"></a>Consulter le rapport DNS
<a name="DNS_Report"> </a>

Le rapport DNS, qui fait partie du rapport Administrateur, détaille toutes les entrées recommandées et connues pour le DNS (Domain Name System) dans les réseaux internes, de périmètre et externes. Si le concepteur a terminé les modifications du diagramme réseau et que toutes les adresses IP et les noms de domaine complets (FQDN) sont définis sur leurs valeurs de production, le rapport DNS fournit une excellente ressource de configuration. Ce rapport peut également servir de document de dépannage opérationnel.

![Rapport d’administration DNS.](../../media/DNS_Report_Admin_Report.png)

Vous devez faire en sorte que votre équipe de gestion DNS examine attentivement le rapport DNS pour vous assurer qu’il n’y a pas d’erreurs qui peuvent provoquer des difficultés pendant le déploiement ou qui peuvent compliquer une session de dépannage.

## <a name="see-also"></a>Voir aussi
<a name="DNS_Report"> </a>

[Consultation des rapports de l’administrateur](/previous-versions/office/lync-server-2013/lync-server-2013-reviewing-the-administrator-reports)