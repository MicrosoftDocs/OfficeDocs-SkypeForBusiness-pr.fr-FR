---
title: 'Lync Server 2013 : Certificats requis pour l’accès des utilisateurs externes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for external user access
ms:assetid: d45b6b10-556f-4b10-b1a7-fb0d0a64a498
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398920(v=OCS.15)
ms:contentKeyID: 48185503
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1b6495dbad5350f94873099985922f1adc198f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736834"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-external-user-access-in-lync-server-2013"></a>Certificats requis pour l’accès des utilisateurs externes dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2016-03-29_

Le logiciel de communications Microsoft Lync Server 2013 prend en charge l’utilisation d’un certificat public unique pour les interfaces externes d’accès et de conférence Web, ainsi que le service d’authentification A/V. L’interface interne Edge utilise généralement un certificat privé émis par une autorité de certification interne, mais peut également utiliser un certificat public, à condition qu’il émane d’une autorité de certification publique de confiance. Le proxy inverse dans votre déploiement utilise un certificat public et chiffre la communication à partir du proxy inverse vers les clients et du proxy inverse vers les serveurs internes en utilisant HTTP (c’est-à-dire, Transport Layer Security sur HTTP).

Vous trouverez ci-après les exigences relatives au certificat public utilisé pour les interfaces externes d’accès et de conférence Web, ainsi que le service d’authentification A/V :

  - Le certificat doit être émis par une autorité de certification publique approuvée prenant en charge le nom alternatif de l’objet. Pour plus d’informations, reportez-vous à l’article 929395 de la base de connaissances Microsoft « partenaires de certification de [http://go.microsoft.com/fwlink/p/?linkId=202834](http://go.microsoft.com/fwlink/p/?linkid=202834)communications unifiées pour Exchange Server et pour Communications Server ».

  - Si le certificat doit être utilisé sur un pool de bords, il doit être créé en tant qu’exportable, avec le même certificat utilisé sur chaque serveur Edge du pool de bords. La configuration requise pour une clé privée interportée est utilisée dans le cadre du service d’authentification A/V, qui doit utiliser la même clé privée sur tous les serveurs Edge du pool.

  - Si vous souhaitez optimiser la durée de fonctionnement de vos services audio et vidéo, consultez les conditions requises pour l’implémentation d’un certificat de service Edge A/v (autrement dit, un certificat de service Edge A/V distinct à partir de l’autre application de certificat Edge externe). Pour plus d’informations, reportez-vous à la section [modifications dans Lync server 2013 qui affectent la planification du serveur Edge](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md), [planifier les certificats de serveur Edge dans Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md) et les [certificats OAuth dans Lync Server 2013 à l’aide de Set-CsCertificate](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate).

  - Le nom du sujet du certificat est le nom de domaine complet (FQDN) du service Edge d’accès ou le protocole VIP d’équilibrage de charge matérielle (par exemple, access.contoso.com). ). Le nom du sujet ne peut pas contenir de caractère générique, il doit s’agir d’un nom explicite.
    
    <div>
    

    > [!NOTE]  
    > Pour Lync Server 2013, il ne s’agit plus d’une exigence, mais elle est toujours recommandée pour la compatibilité avec Office Communications Server.

    
    </div>

  - La liste autre nom de l’objet contient les noms de domaine complets des éléments suivants :
    
      - L’interface externe du service Edge d’accès ou l’adresse VIP d’équilibrage de charge matérielle (par exemple, sip.contoso.com).
        
        <div>
        

        > [!NOTE]  
        > Même si le nom du sujet du certificat est égal au nom de domaine complet du bord d’accès, le nom de l’autre sujet doit également contenir le nom de domaine complet Edge d’accès, car TLS (Transport Layer Security) ignore le nom du sujet et utilise les entrées de nom de l’objet pour Liquid.

        
        </div>
    
      - L’interface ou l’adresse IP (par exemple, webcon.contoso.com) pour la conférence Web.
    
      - Si vous utilisez la configuration automatique du client ou la Fédération, incluez également les noms de domaine complets du domaine SIP utilisés au sein de votre entreprise (par exemple, sip.contoso.com, sip.fabrikam.com).
    
      - Le service Edge A/V n’utilise pas le nom du sujet ou les entrées de noms de substitution d’objet.
    
    <div>
    

    > [!NOTE]  
    > L’ordre des noms de domaine complets dans la liste des noms de remplacement de l’objet n’a pas d’importance.

    
    </div>

Si vous déployez plusieurs serveurs Edge équilibrés sur un site, le certificat de service d’authentification A/V qui est installé sur chaque serveur Edge doit être issu de la même autorité de certification et doit utiliser la même clé privée. Notez que la clé privée du certificat doit être exportable, qu’elle soit utilisée ou non sur un serveur Edge ou sur de nombreux serveurs Edge. Elle doit également être exportée si vous demandez le certificat à partir de n’importe quel ordinateur autre que le serveur Edge. Dans la mesure où le service d’authentification A/V n’utilise pas le nom du sujet ou l’autre nom de l’objet, vous pouvez réutiliser le certificat de point d’accès tant que le nom de l’objet et le nom de l’autre sujet doivent être satisfaits pour le bord d’accès et le Edge de conférence Web, et si la clé privée du certificat est exportable.

Les conditions requises pour le certificat privé (ou public) utilisé pour l’interface interne latérale sont les suivantes :

  - Le certificat peut être émis par une autorité de certification interne ou par un certificat public approuvé.

  - Le nom du sujet du certificat est généralement le nom de domaine complet (FQDN) de l’interface interne Edge ou l’adresse VIP de l’équilibrage de charge matérielle (par exemple, lsedge.contoso.com). Toutefois, vous pouvez utiliser un certificat générique sur le bord interne.

  - Il n’y a pas besoin d’une autre liste de noms d’objet.

Le proxy inverse dans vos demandes de services de déploiement pour :

  - Accès des utilisateurs externes au contenu de la réunion pour les réunions

  - Accès d’un utilisateur externe pour développer et afficher des membres de groupes de distribution.

  - Accès des utilisateurs externes aux fichiers téléchargeables à partir du service de carnet d’adresses

  - Accès des utilisateurs externes au client Lync Web App

  - Accès des utilisateurs externes à la page Web des paramètres de conférence rendez-vous

  - Accès des utilisateurs externes au service d’information d’emplacement

  - Accès d’appareil externe au service de mise à jour de l’appareil et obtention des mises à jour

Le proxy inverse publie les URL des composants internes du serveur Web. Les URL des composants WebPart sont définies sur le directeur, le serveur frontal ou le pool frontal comme **services Web externes** dans le générateur de topologie.

Les entrées de caractères génériques sont prises en charge dans le champ autre nom de l’objet du certificat attribué au proxy inverse. Pour plus d’informations sur la configuration de la demande de certificat pour le proxy inverse, voir [demander et configurer un certificat pour votre proxy http inverse dans Lync Server 2013](lync-server-2013-request-and-configure-a-certificate-for-your-reverse-http-proxy.md).

<div>

## <a name="see-also"></a>Voir aussi


[Prise en charge des certificats comportant des caractères génériques dans Lync Server 2013](lync-server-2013-wildcard-certificate-support.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

