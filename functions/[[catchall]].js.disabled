export async function onRequest(context) {
    const val = await context.env.ANALYTICS.get(context.functionPath);
    if (val === null) {
        await context.env.ANALYTICS.put(context.functionPath, 1);
        return new Response({ status: 418 });
    }
    const hitcount = await context.env.ANALYTICS.get(context.functionPath);
    await context.env.ANALYTICS.put(context.functionPath, parseInt(hitcount)+1);

    return new Response({ status: 418 });
}