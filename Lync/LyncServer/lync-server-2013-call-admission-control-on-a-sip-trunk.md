---
title: 'Lync Server 2013 : Contrôle d’admission des appels sur une jonction SIP'
TOCTitle: Contrôle d’admission des appels sur une jonction SIP
ms:assetid: 7eada098-3d47-4be2-839f-8f87d582efe8
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398632(v=OCS.15)
ms:contentKeyID: 49297859
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Contrôle d’admission des appels sur une jonction SIP dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2012-09-22_

Pour déployer le contrôle d’admission des appels sur une jonction SIP, vous créez un site réseau pour représenter le fournisseur de services de téléphonie Internet (ITSP). Pour appliquer la stratégie de bande passante sur la jonction SIP, vous créez une stratégie intersite entre le site réseau dans votre entreprise et le site réseau créé pour représenter le fournisseur de services de téléphonie Internet.

La figure suivante montre un exemple de déploiement du contrôle d’admission des appels sur une jonction SIP.

**Configuration du contrôle d’admission des appels sur une jonction SIP**

![Diagramme de jonction SIP de Contrôle d’admission des appels](images/Gg398632.276c0d8f-1dd5-4883-8499-c202399ddbe9(OCS.15).jpg "Diagramme de jonction SIP de Contrôle d’admission des appels")

Pour configurer le contrôle d’admission des appels sur une jonction SIP, vous devrez exécuter les tâches suivantes pendant le déploiement du contrôle d’admission des appels :

1.  Créez un site réseau pour représenter le fournisseur de services de téléphonie Internet. Associez le site réseau à une région réseau appropriée, et allouez une bande passante nulle pour l’audio et la vidéo pour ce site réseau. Pour plus d’informations, reportez-vous à [Configurer les sites réseau pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md) dans la documentation de déploiement.
    
    > [!NOTE]  
    > Pour le fournisseur de services de téléphonie Internet, cette configuration de site réseau n’est pas fonctionnelle. Les valeurs de stratégie de bande passante sont en fait appliquées à l’étape 2.

2.  Créez un lien intersite pour la jonction SIP à l’aide des valeurs de paramètre pertinentes pour le site créé à l’étape 1. Par exemple, utilisez le nom du site réseau dans votre entreprise comme valeur du paramètre NetworkSiteID1 et le site réseau du fournisseur de services de téléphonie Internet comme valeur du paramètre NetworkSiteID2. Pour plus d’informations, reportez-vous à [Créer des stratégies inter-sites réseau](lync-server-2013-create-network-intersite-policies.md) dans la documentation de déploiement. Consultez également la documentation de Lync Server Management Shell pour l’applet de commande New-CsNetworkInterSitePolicy.

3.  Récupérez l’adresse IP du point de terminaison multimédia du contrôleur SBC auprès de votre fournisseur de services de téléphonie Internet. Ajoutez cette adresse IP avec un masque de sous-réseau de 32 au site réseau qui représente le fournisseur de services de téléphonie Internet. Pour plus d’informations, reportez-vous à [Association d’un sous-réseau à un site réseau dans Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).

