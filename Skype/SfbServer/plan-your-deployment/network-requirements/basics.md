---
title: Notions de base du système DNS
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 inclut des logiciels intégrés qui peuvent fournir des services DNS, de sorte que vous pouvez consulter la documentation disponible telle que le Guide du scénario de stratégie DNS. Si vous le souhaitez, vous pouvez choisir une solution tierce.
ms.openlocfilehash: c1084a756a79ebcf15b8e99eef049690b5dcd9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297273"
---
# <a name="dns-basics"></a>Notions de base du système DNS
 
Windows Server 2016 inclut des logiciels intégrés qui peuvent fournir des services DNS, de sorte que vous pouvez consulter la documentation disponible telle que le [Guide du scénario de stratégie DNS](https://docs.microsoft.com/windows-server/networking/dns/deploy/dns-policy-scenario-guide). Si vous le souhaitez, vous pouvez choisir une solution tierce.
  
Nous vous conseillons de dédier un serveur spécifique dans votre implémentation pour fournir DNS. Il est possible que vous ayez configuré ce service sur l’un des serveurs dédiés à l’un des rôles de serveur Skype entreprise, mais si celui-ci a fait partie d’un pool et qu’il a été mis en place en raison de sa désactivation, Skype entreprise ne fonctionne pas tant que les services DNS n’ont pas été rétablis.
  
## <a name="dns-records"></a>Enregistrements DNS

Chaque mappage d’un nom à une adresse IP (qui peut être une adresse IPv4 ou IPv6) est stocké dans un enregistrement DNS sur le serveur DNS. Le nom est décrit dans le rapport DNS en particulier en tant que nom de domaine complet (FQDN), un nom de domaine complet. Si *contoso.com* est un nom de domaine valide, il s’agit de l’abréviation de * \*. contoso.com* , donc il est ambigu et peut faire référence à n’importe quel serveur du domaine. Un exemple d’un nom de domaine complet qui fera référence à un serveur unique de votre domaine peut être **meeting01.contoso.com**.
  
> [!IMPORTANT]
> Par défaut, le nom de l’ordinateur d’un ordinateur qui n’est pas joint à un domaine est un nom d’hôte, et non un nom de domaine complet. Le générateur de topologie utilise les noms de domaine complets et non les noms d’hôte. Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur qui sera déployé en tant que serveur de périphérie non lié à un domaine. **Utiliser uniquement les caractères standard** (y compris A-Z, a-z, 0-9 et les traits d’Union) lorsque vous attribuez des noms de domaine complets aux serveurs exécutant Skype entreprise Server. N’utilisez pas les caractères ou traits de soulignement Unicode. Souvent, les caractères non standard dans un FQDN ne sont pas pris en charge par le DNS externe et les autorités de certification publique (quand le FQDN doit être assigné au SN dans le certificat).
  
En plus d’une adresse IP, le nom de domaine complet ( **** FQDN) peut correspondre à une adresse IP virtuelle. Une adresse IP virtuelle est une adresse IP qui ne correspond pas à une interface réseau physique réelle. Un VIP pointe souvent vers un ensemble de serveurs exécutant un rôle de serveur, ou vers une paire de serveurs configurés pour la redondance et la tolérance de panne.
  
Il existe plusieurs types d’enregistrements DNS, les plus pertinents pour cette discussion sont les suivants: 
  
- **A** : enregistrement d’adresse ou enregistrement d’hôte, renvoie une adresse IPv4 32 bits. Le plus souvent, il est utilisé pour mapper les noms d’hôte à une adresse IP de l’hôte.
    
- **Aaaa** : enregistrement d’adresse IPv6. Renvoie une adresse IPv6 128 bits. Le plus souvent, il est utilisé pour mapper les noms d’hôte à une adresse IP de l’hôte.
    
- **CNAME** : enregistrement de nom canonique. Cela résout un nom en un autre: la recherche DNS effectue une nouvelle recherche avec le nouveau nom.
    
- **SRV** — un enregistrement de service (enregistrement SRV) spécifie un service (processus sur un serveur) sur lequel est consulté un port et une combinaison d’adresses IP spécifiques. Les noms des services nécessitant un enregistrement de service sont fixes et ne peuvent pas être personnalisés de la même façon que dans votre domaine SIP. Certains services d’utilisateurs utilisent des URL simples. Un enregistrement SRV doit pointer vers un emplacement dans le même domaine SIP, donc si vous avez plusieurs domaines, vous devez disposer de plusieurs enregistrements SRV pour un service donné.
    
## <a name="how-to-choose-a-sip-domain-name"></a>Choisir un nom de domaine SIP
<a name="BK_NameSIP"> </a>

Le nom de domaine SIP d’une organisation est généralement aligné sur les adresses de messagerie fournies aux utilisateurs. Si un utilisateur de votre organisation aura une adresse de messagerie telle que Brown@contoso.com, le \<domaine\> SIP préféré pour une organisation avec le nom de domaine contoso.com est simplement contoso.com.
  
### <a name="multiple-sip-domains"></a>Domaines SIP multiples

 Dans certains cas, votre organisation a peut-être besoin de plusieurs domaines SIP. Par exemple, si Fabrikam.com a été acquis par contoso.com, il se peut que vous deviez créer un nouveau domaine SIP reconnu par Skype entreprise Server et qui acceptera la connexion. Lorsque vous procédez ainsi, vous devez créer un ensemble supplémentaire de tous les enregistrements DNS qui utilisent contoso.com, avec de nouveaux noms de domaine complets indiquant où envoyer les demandes de fabrikam.
  
## <a name="dns-load-balancing"></a>DNS Load Balancing
<a name="BK_NameSIP"> </a>

Vous pouvez utiliser DNS pour partager la charge de trafic entre plusieurs serveurs configurés en tant que pool de serveurs. Pour ce faire, vous devez créer plusieurs enregistrements A pour le nom de domaine complet (FQDN) du pool, chacun pointant vers l’adresse IP d’un nœud dans le pool.
  
Voir [équilibrage de charge DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) pour découvrir d’autres discussions concernant l’équilibrage de charge.
  

