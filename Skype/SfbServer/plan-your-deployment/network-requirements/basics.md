---
title: Principes de base
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 dispose de logiciels intégrés qui peuvent fournir des services DNS. Vous pouvez donc consulter la documentation disponible, telle que le Guide du scénario de stratégie DNS. Vous pouvez choisir une solution tierce si vous préférez.
ms.openlocfilehash: 2ee4ee73a6cb85ac51785a47e4f0ec86d581b809
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58602339"
---
# <a name="dns-basics"></a>Principes de base
 
Windows Server 2016 dispose d’un logiciel intégré qui peut fournir des services DNS. Vous pouvez donc consulter la documentation disponible, telle que le Guide de scénario de stratégie [DNS.](/windows-server/networking/dns/deploy/dns-policy-scenario-guide) Vous pouvez choisir une solution tierce si vous préférez.
  
Nous vous recommandons de dédier un serveur spécifique dans votre implémentation à fournir le DNS. Vous pouvez éventuellement le configurer sur l’un des serveurs dédiés à l’un des rôles serveur Skype Entreprise, mais si ce serveur faisait également partie d’un pool et qu’il a été désaffecté par un accident Skype Entreprise ne fonctionnerait pas tant que les services DNS n’auraient pas été rétablis.
  
## <a name="dns-records"></a>Enregistrements DNS

Chaque mappage d’un nom à une adresse IP (et qui peut être une adresse IPv4 ou IPv6) est stocké dans un enregistrement DNS sur le serveur DNS. Le nom est décrit dans le rapport DNS en tant que nom de domaine complet ( nom de domaine complet). Bien *que contoso.com* soit un nom de domaine valide, il s’agit d’un raccourci pour *\* .contoso.com.* Il est donc ambigu et peut éventuellement faire référence à n’importe quel serveur du domaine. Un exemple de nom de domaine public (FQDN) qui fait référence à un serveur unique dans **votre domaine peut être meeting01.contoso.com**.
  
> [!IMPORTANT]
> Par défaut, le nom d’ordinateur d’un ordinateur qui n’est pas joint à un domaine est un nom d’hôte et non un nom de domaine complet. Le Générateur de topologie utilise des noms de domaine noms de domaine (FQDN), et non des noms d’hôte. Par conséquent, vous devez configurer un suffixe DNS sur le nom de l’ordinateur à déployer en tant que serveur Edge non membre d’un domaine. Utilisez uniquement des caractères **standard** (Y compris A-Z, a-z, 0-9 et tirets) lors de l’affectation de noms de noms de famille à vos serveurs exécutant Skype Entreprise Server. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans les noms de domaines complets ne sont généralement pas pris en charge par les DNS externes et les autorités publiques de certification (c’est-à-dire lorsque le nom de domaine complet doit être affecté à l’élément SN (Subject Name) du certificat).
  
En plus d’une adresse IP, le FQDN peut être mappé sur une **adresse IP** virtuelle. Une adresse IP ip ne correspond pas à une interface réseau physique réelle. Une vip pointe souvent vers un pool de serveurs qui exécutent un rôle serveur ou vers une paire de serveurs configurés pour la redondance et la tolérance de panne.
  
Il existe plusieurs types d’enregistrement DNS, ceux qui sont les plus pertinents pour cette discussion sont : 
  
- **R** : enregistrement d’adresse ou enregistrement d’hôte, renvoie une adresse IPv4 32 bits. Le plus couramment utilisé pour ma mapnner les noms d’hôte à une adresse IP de l’hôte.
    
- **AAAA** : enregistrement d’adresse IPv6. Renvoie une adresse IPv6 128 bits. Le plus couramment utilisé pour ma mapnner les noms d’hôte à une adresse IP de l’hôte.
    
- **CNAME :** enregistrement de nom canonique. Cela résout un nom en un autre : la recherche DNS va réessayer la recherche avec le nouveau nom.
    
- **SRV** : un enregistrement de service (enregistrement SRV) spécifie un service (processus sur un serveur) accessible sur un port et une combinaison IP spécifiques. Les noms des services nécessitant un enregistrement de service sont résolus et ne peuvent pas être personnalisés au-delà de leur faire partie de votre domaine SIP. Certains services d’utilisateurs utilisent des URL simples. Un enregistrement SRV doit pointer vers un emplacement dans le même domaine SIP. Ainsi, si vous avez plusieurs domaines, vous aurez besoin de plusieurs enregistrements SRV pour un service donné.
    
## <a name="how-to-choose-a-sip-domain-name"></a>Comment choisir un nom de domaine SIP
<a name="BK_NameSIP"> </a>

Le nom de domaine SIP d’une organisation s’aligne généralement sur les adresses de messagerie données à ses utilisateurs. Si un utilisateur de votre organisation a une adresse de messagerie telle que Brown@contoso.com, la préférence pour une organisation avec le nom de domaine contoso.com est \<sip-domain\> simplement contoso.com.
  
### <a name="multiple-sip-domains"></a>Plusieurs domaines SIP

 Dans certains cas, votre organisation peut avoir besoin de plusieurs domaines SIP. Par exemple, si Fabrikam.com a été acquis par contoso.com, vous devrez peut-être créer un domaine SIP à partir de Skype Entreprise Server reconnaîtra et acceptera la connexion. Lorsque vous faites cela, vous devez créer un ensemble supplémentaire de tous les enregistrements DNS qui utilisent contoso.com, avec de nouveaux FQDN qui indiquent où envoyer des demandes pour Fabrikam.
  
## <a name="dns-load-balancing"></a>Équilibrage de charge DNS
<a name="BK_NameSIP"> </a>

Vous pouvez utiliser DNS pour partager la charge du trafic entre plusieurs serveurs qui sont configurer en tant que pool de serveurs. Pour ce faire, vous devez créer plusieurs enregistrements A pour le FQDN du pool, chacun pointant vers l’adresse IP d’un nœud du pool.
  
Voir [l’équilibrage de charge DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) pour d’autres discussions sur l’équilibrage de charge.
