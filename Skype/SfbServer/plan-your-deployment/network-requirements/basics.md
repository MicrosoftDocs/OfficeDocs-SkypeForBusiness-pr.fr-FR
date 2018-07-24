---
title: Notions de base sur DNS
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2618cfa1-2e2c-4f1d-a5e5-70a0286591a7
description: Windows Server 2016 a logiciel intégré qui peut fournir des services DNS, vous pouvez donc à consulter la documentation disponible telles que le Guide de scénario de stratégie DNS. Vous pouvez choisir une solution tierce si vous préférez.
ms.openlocfilehash: 545b196320ae3b4297d9944ff29c105eb1ce219b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20981078"
---
# <a name="dns-basics"></a>Notions de base sur DNS
 
Windows Server 2016 a logiciel intégré qui peut fournir des services DNS, vous pouvez donc à consulter la documentation disponible telles que le [Guide de scénario de stratégie DNS](https://docs.microsoft.com/en-us/windows-server/networking/dns/deploy/dns-policy-scenario-guide). Vous pouvez choisir une solution tierce si vous préférez.
  
Nous vous recommandons de meilleure pratique dédier un serveur spécifique dans votre implémentation de fournir le DNS. Vous pouvez éventuellement configurer il sur un des serveurs dédiés à un de la Skype pour les rôles de serveur Business, mais si ce serveur a été également partie d’un pool et a été désactivé par accident Skype pour Business serait mal fonctionner jusqu'à ce que les services DNS ont été rétablies.
  
## <a name="dns-records"></a>Enregistrements DNS

Chaque mappage de nom à une adresse IP (et qui peut être une adresse IPv4 ou IPv6) est stocké dans un enregistrement DNS sur le serveur DNS. Le nom est décrit dans le rapport DNS spécifiquement comme nom de domaine complet, un nom de domaine complet. *Contoso.com* est un nom de domaine valide, il est l’abréviation de * \*. contoso.com* , de sorte qu’il est ambigu et peut éventuellement faire référence à n’importe quel serveur du domaine. Un exemple de nom de domaine complet qui fait référence à un serveur unique dans votre domaine peut être **meeting01.contoso.com**.
  
> [!IMPORTANT]
> Par défaut, le nom d’un ordinateur qui n’est pas joint à un domaine est un nom d’hôte, et non un nom de domaine complet. Le Générateur de topologie utilise des noms de domaine complets, pas les noms d’hôte. Vous devez donc configurer un suffixe DNS sur le nom de l’ordinateur à déployer en tant que serveur Edge non joint à un domaine. **Utiliser des caractères standard uniquement** (y compris les A-Z, a-z, 0-9 et tirets) lors de l’affectation de noms de domaine complets pour vos serveurs exécutant Skype pour Business Server. N’utilisez ni caractère Unicode ni trait de soulignement. Les caractères non standard dans les noms de domaine complets ne sont généralement pas pris en charge par les systèmes DNS externes et les autorités publiques de certification (lorsque le nom de domaine complet doit être affecté à l’élément SN (Subject Name) du certificat).
  
En plus d’une adresse IP, le nom de domaine complet peut mapper à une **adresse IP virtuelle** — une adresse IP virtuelle. Une adresse IP virtuelle est une adresse IP qui ne correspond pas à une interface réseau physique. Souvent, une adresse IP virtuelle pointe vers un pool de serveurs qui effectuent un rôle de serveur, ou à une paire de serveurs configurés pour la redondance et la tolérance de panne.
  
Il existe plusieurs types d’enregistrement DNS, ceux qui est les plus pertinentes pour cette discussion sont : 
  
- **A** — un enregistrement d’adresse ou l’enregistrement d’hôte, cette propriété renvoie une adresse IPv4 de 32 bits. Plus fréquemment utilisés pour mapper des noms d’hôte à une adresse IP de l’hôte.
    
- **AAAA** : un enregistrement d’adresse IPv6. Renvoie une adresse IPv6 de 128 bits. Plus fréquemment utilisés pour mapper des noms d’hôte à une adresse IP de l’hôte.
    
- **CNAME** , un enregistrement de nom canonique. Cela suffit à résoudre un nom à un autre : la recherche DNS système recommencer la recherche avec le nouveau nom.
    
- **SRV** , un enregistrement de Service (SRV enregistrement) spécifie un service qui se trouve sur une combinaison de IP et un port spécifique (il s’agit d’un processus sur un serveur). Les noms des services nécessitant un enregistrement de service sont fixes et ne peuvent pas être personnalisées au-delà de ce qui les rend une partie de votre domaine SIP. Certains services d’utilisateur utilisent des URL simples. Un enregistrement SRV doit pointer vers un emplacement dans le même domaine SIP, afin que si vous disposez de plusieurs domaines, vous devez plusieurs enregistrements SRV pour un service donné.
    
## <a name="how-to-choose-a-sip-domain-name"></a>Choisir un nom de domaine SIP
<a name="BK_NameSIP"> </a>

Nom de domaine SIP d’une organisation s’aligne généralement sur les adresses de messagerie données à ses utilisateurs. Si un utilisateur dans votre organisation doit recevoir une adresse de messagerie comme Brown@contoso.com, préférable \<domaines sip\> pour une organisation avec le domaine contoso.com nom est simplement contoso.com.
  
### <a name="multiple-sip-domains"></a>Plusieurs domaines SIP

 Votre organisation devront dans certains cas, plusieurs domaines SIP. Par exemple, si Fabrikam.com a été acquis par contoso.com, vous devrez peut-être créer un domaine SIP que Skype pour Business Server reconnaît et accepte les connexions à partir de. Lorsque vous effectuez cette opération, vous devez créer un ensemble de tous les enregistrements DNS qui utilisent contoso.com, avec le nouveau nom de domaine complet qui indiquent où envoyer les demandes de Fabrikam supplémentaire.
  
## <a name="dns-load-balancing"></a>Équilibrage de charge DNS
<a name="BK_NameSIP"> </a>

Vous pouvez utiliser DNS pour partager la charge du trafic entre plusieurs serveurs qui sont configurés comme un pool de serveurs. Pour ce faire, vous créez plusieurs enregistrements A pour le nom de domaine complet du pool, chacun d'entre eux pointe vers l’adresse IP d’un nœud du pool.
  
Pour plus d’informations d’équilibrage de charge, voir [équilibrage de charge DNS](../../plan-your-deployment/edge-server-deployments/advanced-edge-server-dns.md#DNSLB) .
  

