Implement SensorEventListener.

        SensorManager sensorManager = (SensorManager) getSystemService(SENSOR_SERVICE);
        if(sensorManager != null)
        {
            Sensor proximitySensor = sensorManager.getDefaultSensor(Sensor.TYPE_PROXIMITY);
            if(proximitySensor != null)
            {
                sensorManager.registerListener(this, proximitySensor, SensorManager.SENSOR_DELAY_FASTEST);
            }
        }

    @Override
    public void onSensorChanged(SensorEvent event) {
        if(event.sensor.getType() == Sensor.TYPE_PROXIMITY)
        {
            ((TextView) findViewById(R.id.proxiTextView)).setText(String.format("Proximity Sensor Value: %s", event.values[0]));
        }
    }

    @Override
    public void onAccuracyChanged(Sensor sensor, int accuracy) {

    }
